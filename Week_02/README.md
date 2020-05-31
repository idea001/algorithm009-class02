# 学习笔记

## hashmap分析:

HashMap在jdk1.8后采用的是数组+链表+红黑树实现的,jdk1.8之前都是数组+链表实现的,为什么要引入红黑树呢?是因为链表的查询操作是o(N)的时间复杂度,hashmap中查询时如果节点很多的话,转化成红黑树,可以提高很大的效率,因为红黑树中,增删改查都是o(log N)的复杂度.

```java

public class HashMap<K,V> extends AbstractMap<K,V>
    implements Map<K,V>, Cloneable, Serializable {
    private static final long serialVersionUID = 362498820763181265L;
    //默认容量，1向左移位4个，也就是2的4次方为16
    static final int DEFAULT_INITIAL_CAPACITY = 1 << 4;
    //最大容量为2的30次方。
    static final int MAXIMUM_CAPACITY = 1 << 30;
    //加载因子是用于扩容使用。
    static final float DEFAULT_LOAD_FACTOR = 0.75f;
    //当某个桶节点数量大于8时，会转换为红黑树。
    static final int TREEIFY_THRESHOLD = 8;
    //当某个桶节点数量小于6时，会转换为链表(当前是红黑树结构)
    static final int UNTREEIFY_THRESHOLD = 6;
    //当整个hashMap中元素数量大于64时，也会进行转为红黑树结构。
    static final int MIN_TREEIFY_CAPACITY = 64;
    //存储元素的数组，transient关键字表示该属性不能被序列化
    transient Node<K,V>[] table;
    //将数据转换成set的另一种存储形式，这个变量主要用于迭代功能。
    transient Set<Map.Entry<K,V>> entrySet;
    //元素数量
    transient int size;
    //统计该map修改的次数
    transient int modCount;
    //临界值，也就是元素数量达到临界值时，会进行扩容。
    int threshold;
    //是加载因子
    final float loadFactor;  
```

