# 189.旋转数组

暴力法,两层循环定义临时变量求解

```java
public class Solution {
    public void rotate(int[] nums, int k) {
		int temp,previous;
		for(int i=0;i<k;i++){
		previous =nums[nums.length-1];
			for(int j=0;j<nums.length;j++){
				temp=num[j];
				num[j]=previous;
				previous=temp;
		}	
}
        
时间复杂度:O(n*k),假如有k个元素,每个元素都要移动
空间复杂度:O(1)
```

优化后的代码:定义开始指针和结束指针,然后单独写个反转方法

```java
public class Solution {
  public void rotate(int[] nums, int k) {
    k %= nums.length;
    reverse(nums, 0, nums.length - 1);
    reverse(nums, 0, k - 1);
    reverse(nums, k, nums.length - 1);
}

public void reverse(int[] nums, int start, int end) {
    while (start < end) {
        int temp = nums[start];
        nums[start] = nums[end];
        nums[end] = temp;
        start++;
        end--;
    }
}
}
```

