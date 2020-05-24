# 66.加一

```
思路:
1.用i变量从数组最后一位向前找，找到第一个不为9的下标，对其加1，然后从i开始到数组结尾全置0，然后返回
2.边界条件：如果整个数组全为9，则新建数组，长度为n+1,然后将新数组第一位置1,返回新数组。

class Solution {
    public int[] plusOne(int[] digits) {
        int n=digits.length;
        int i=n-1;
        for(;i>=0;i--){
            if(digits[i]!=9){
                break;
            }
        }
        if(i==-1){
            int []r=new int[n+1];
            r[0]=1;
            return r;
        }
        digits[i]=digits[i]+1;
        for(int j=i+1;j<n;j++){
            digits[j]=0;
        }
        return digits;
    }
}
时间复杂度:O(n)


```

