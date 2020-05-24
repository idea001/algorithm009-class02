# 改写deque

```
源代码:

Deque<String> deque = new LinkedList<String>();

deque.push("a");
deque.push("b");
deque.push("c");
System.out.println(deque);

String str = deque.peek();
System.out.println(str);
System.out.println(deque);
while (deque.size() > 0) {
    System.out.println(deque.pop());
}
System.out.println(deque);

```

```
修改后:

Deque<String> deque = new LinkedList<String>();

deque.addFirst("a");
deque.addFirst("b");
deque.addFirst("c");
System.out.println(deque);

String str = deque.peekFirst();
System.out.println(str);
System.out.println(deque);
while (deque.size() > 0) {
    System.out.println(deque.removeFirst());
}
System.out.println(deque);

```

```
deque源码分析:
add方法:往队列添加元素，如果添加成功则返回true，如果容量限制导致添加失败则抛出异常
offer方法:将指定的元素插入队列中,当使用容量受限制的队列时,它只能插入一个元素,会抛出异常
remove方法:检索并删除队列的头,队列如果为空会抛出异常
poll方法:检索删除队列的头,如果队列为空返回null
element方法:检索但是不会删除队列的头,只会抛出一个异常

```

```
PriorityQueue源码解析:
PriorityQueue是非线程安全的,无序存储着最小元素,入队是插入元素的实现,出队是删除元素的实现

```

