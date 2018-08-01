* # 问题分析
给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。
* # 编程实现
```c
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
         int n = nums.size();  
        int max = nums[0];
        int sum = 0;
        for(int i=0;i<n;i++)
        {
            sum += nums[i];
            if(sum > max)  
            {  
                max = sum;  
            }  
            if(sum < 0)  
            {  
                sum = 0; 
            }  
        }  
        return max;  
    }
};
```
```python
class Solution:
    def maxSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        maxSum = []
        maxSum.append(nums[0])
        
        for i  in range(1,len(nums)):
            maxSum.append(max(nums[i],maxSum[i-1]+nums[i]))
        
        return max(maxSum)
```
* # 总结体会
  将字串和为负数的字串丢掉，这样可以大大减少计算量，使时间复杂度达到O(n)。
用动态规划的思想，maxSum[i]=max(nums[i],nums[i]+max[i-1]),maxSum[i]表示为到第i个元素的最大子序和。
