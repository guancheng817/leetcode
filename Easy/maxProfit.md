* # 问题分析
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

设计一个算法来计算你所能获取的最大利润。你可以尽可能地完成更多的交易（多次买卖一支股票）。

注意：你不能同时参与多笔交易（你必须在再次购买前出售掉之前的股票）。
Say you have an array for which the ith element is the price of a given stock on day i.

Design an algorithm to find the maximum profit. You may complete as many transactions as you like (i.e., buy one and sell one share of the stock multiple times).
* # 编程实现
```c
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int j;  
        int maxProfit = 0;  
        for(int i = 1; i < prices.size(); i++)
        { 
            j = prices[i] - prices[i - 1];  
            if(j > 0)
            {  
                maxProfit += j;  
            }  
        }  
        return maxProfit;  
    }
};
```
* # 总结体会
由于不限购买次数，所以只要能赚钱，就卖出即可，然后统计利润。