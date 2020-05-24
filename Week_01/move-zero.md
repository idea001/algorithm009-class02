# 283.移动零

思路:不为0的用一个变量进行标记,结束后对标记的全部设为0

```
class Solution {
    public void moveZeroes(int[] nums) {
        int j = 0;
        for (int i = 0; i< nums.length; i++) {
            if (nums[i] != 0) {
                if(i != j) {
                    nums[j] = nums[i];
                    nums[i] = 0;
                }
                j++;
            }
        }
    }
}
时间复杂度:O(n)
```

