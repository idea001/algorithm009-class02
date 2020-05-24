# 1.两数之和

```
1.暴力法,两层for循环
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[j] == target - nums[i]) {
                    return new int[] { i, j };
                }
            }
        }
        throw new IllegalArgumentException("No two sum solution");
    }
}

```



```
2.hash映射
class Solution {
    public int[] twoSum(int[] nums, int target) {
	//创建map集合
        Map<Integer,Integer> map =new HashMap<>();
        int length=nums.length;
        for(int i=0;i<length;i++){
            int value=target-nums[i];
			//如果map存在此差值,则返回
            if(map.containsKey(value)){
                return new int[]{map.get(value),i};
            }
			//将该数组的值存入map中
            map.put(nums[i],i);
        }
        return null;
        
    }
}
时间复杂度:O(n)
}
空间复杂度:O(n)
```

