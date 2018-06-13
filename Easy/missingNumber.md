* # 
问题分析
给出一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。

* # 编程实现

```c

class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size(),sum=0;

        
        for(int i=0;i<n;i++)
        {
            sum = sum+nums[i];
        }
         
        return n*(n+1)/2-sum;
    }
};

```

```c
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int result=0;
        for(int i=0;i<=n;++i)
            result^=i;
        for(int i=0;i<n;++i)
            result^=nums[i];
        return result;
    }
};
```
* # 总结体会

 用数学的方法求解即可，将0-n的总和减去数组中所有数的总和。
第二种解法，把0到n异或一遍，再对给定数组异或一遍，所得的结果就是缺失的数。