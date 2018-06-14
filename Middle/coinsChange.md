* # 问题分析
You are given coins of different denominations and a total amount of money amount. Write a function to compute the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

给定不同面额的硬币 coins 和一个总金额 amount。编写一个函数来计算可以凑成总金额所需的最少的硬币个数。如果没有任何一种硬币组合能组成总金额，返回 -1。



* # 编程实现
```c
class Solution {
public:
    int coinChange(vector<int>& coins, int amount) {
        vector<int> dp(amount+1, 100);
        dp[0] = 0;
        for(int i = 0; i < coins.size(); i++){
            for(int j = 0; j <= amount - coins[i]; j++){
                dp[j+coins[i]] = min(dp[j+coins[i]], dp[j]+1);
            }
        }
        if(dp[amount] == 100)
            return -1;
        return dp[amount];
    }
};
```

* # 总结体会
 用动态规划，设dp[j] 为兑换amount最少的硬币数。

则有：dp[j + coins[i] ] = min(dp[j + coins[i] ] , dp[j] + 1）

