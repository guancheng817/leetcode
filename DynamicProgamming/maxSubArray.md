## question
给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。


输入: [-2,1,-3,4,-1,2,1,-5,4],
输出: 6
解释: 连续子数组 [4,-1,2,1] 的和最大，为 6。
## code
```python

class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        dp = [0 for i in range(len(nums))]

        dp[0] = nums[0]
        res = nums[0]
        for i in range(1, len(nums)):
            dp[i] = max(dp[i-1],0)+ nums[i]
            res = max(res, dp[i])

        return res
```

## analysis
利用动态规划来求解
1. 状态定义: dp[i] 表示前 i 个元素的最大连续子数组的和
2.  状态初始化，数组中第一个元素的最大和就是第一个元素值
3. 转移方程：dp[i] = max(dp[i - 1], 0) + nums[i]
