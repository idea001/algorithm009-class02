# 26.删除排序数组中的重复项

解题思路:

定义p和q指针,如果p和q相等,则q后移一位,如果不相等将q位置的元素复制到p+1上,p再后移一位,q后移一位

```java
class Solution {
     public int removeDuplicates(int[] nums) {
    if(nums == null || nums.length == 0) return 0;
    int p = 0;
    int q = 1;
    while(q < nums.length){
        if(nums[p] != nums[q]){
            nums[p + 1] = nums[q];
            p++;
        }
        q++;
    }
    return p + 1;
}
}
时间复杂度:O(n)
空间复杂度:O(1)
    
    
优化后的代码:
class Solution {
public int removeDuplicates(int[] nums) {
    int i = 0;
    for (int n : nums)
        if (i == 0 || n > nums[i-1])
            nums[i++] = n;
    return i;
}
}
```

