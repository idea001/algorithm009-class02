# 21.合并两个有序链表

```
class Solution {
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        if(l1 == null){
			return l2;
		}
		else if(l2 == null){
				return l1;
		}
		else if(l1.val < l2.val){
			l1.next=mergeTwoLists(l1.next,l2);
				return l1;
		}
		else{
			l2.next=mergeTwoLists(11,l2.next);
				return l2;
		}

    }
}
时间复杂度:O(a+b),假设a和b分别是两个链表的长度
空间复杂度:O(a+b)
```

优化解法:

```java
public ListNode mergeTwoLists(ListNode l1, ListNode l2){
		if(l1 == null) return l2;
		if(l2 == null) return l1;
		if(l1.val < l2.val){
			l1.next = mergeTwoLists(l1.next, l2);
			return l1;
		} else{
			l2.next = mergeTwoLists(l1, l2.next);
			return l2;
		}
}
```

