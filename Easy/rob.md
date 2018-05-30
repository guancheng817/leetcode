* # 问题分析
You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security system connected and it will automatically contact the police if two adjacent houses were broken into on the same night.

Given a list of non-negative integers representing the amount of money of each house, determine the maximum amount of money you can rob tonight without alerting the police.
是一个专业的小偷，计划偷窃沿街的房屋。每间房内都藏有一定的现金，影响你偷窃的唯一制约因素就是相邻的房屋装有相互连通的防盗系统，如果两间相邻的房屋在同一晚上被小偷闯入，系统会自动报警。

给定一个代表每个房屋存放金额的非负整数数组，计算你在不触动警报装置的情况下，能够偷窃到的最高金额。
* # 编程实现
```c
class Solution {
public:
    int rob(vector<int>& nums) {
        int n = nums.size();
        if(n == 0)
            return 0;
        if(n == 1)
            return nums[0];
        int sum1,sum2; //sum1表示打劫到第i家的总收益，sum2表示打劫到第i-2家的总收益
        sum1 = sum2 = 0;
        for(int i = 0; i < n; i++){
            int tmp = sum1;
            sum1 = max(sum1, sum2+nums[i]);
            sum2 = tmp;
        }
        return sum1;
    }
};
```
* # 总结体会
  设sum1为打劫到第i家的总收益，sum2为表示打劫到第i-2家的总收益，则有递推关系sum[i]=max(sum[i-1],sum2+nums[i])，即打劫到第i-1家时的收益与打劫到第i-2家的收益加上打劫第i家获得的金钱取其中的最大值。