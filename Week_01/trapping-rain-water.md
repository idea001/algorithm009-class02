# 42.接雨水

```java
思路:
1.两端的不用考虑,
2.找出左边的最高和右边的最高
3.找出较小的,然后较小的应该大于当前的高度才会有水

class Solution {
   public int trap(int[] height) {
    int sum = 0;
    for (int i = 1; i < height.length - 1; i++) {
        int max_left = 0;
        for (int j = i - 1; j >= 0; j--) {
            if (height[j] > max_left) {
                max_left = height[j];
            }
        }
        int max_right = 0;
        for (int j = i + 1; j < height.length; j++) {
            if (height[j] > max_right) {
                max_right = height[j];
            }
        }
        int min = Math.min(max_left, max_right);
        if (min > height[i]) {
            sum = sum + (min - height[i]);
        }
    }
    return sum;
}
}
时间复杂度:O(n*n),遍历每一列是n,找出两端的最高也是n

```

