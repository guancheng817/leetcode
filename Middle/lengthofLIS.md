* # 问题分析
Given an unsorted array of integers, find the length of longest increasing subsequence.
给定一个无序的整数数组，找到其中最长上升子序列的长度。

* # 编程实现
```c
class Solution {
public:
    int lengthOfLIS(vector<int>& nums) {
            
    vector<int> vec(nums.size());
    
    int sum=0;  
    for(int i=0;i<nums.size();i++){  
        vec[i]=1;
        for(int j=0;j<i;j++){  
            if(nums[i]>nums[j])  
            vec[i]=max(vec[i],vec[j]+1);  
        } 
        
        sum=max(sum,vec[i]);  
    }  
        
    return sum; 
    }
};
```
```python
class Solution:
    def lengthOfLIS(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        num = 0
        dp = [0]*len(nums)
        for i in range(len(nums)):
            dp[i]=1
            for j in range(i):
                if nums[i]>nums[j] and dp[j]+1 > dp[i]:
                    dp[i] = dp[j]+1
            
            num = max(dp[i],num)
                    
        return num
```

* # 总结体会
vec[i]表示以到第i个数字的最长上升子序列的长度，只看这个数字之前的数字，如果比他之前的数字大，那么选择这个数字之后最大上升序列长度+1，即有关系式vec[i]=max(vec[i],vec[j]+1)。
用python解同理，dp[i]=max{1,dp[j]+1}(j<i and nums[i]>nums[j])
