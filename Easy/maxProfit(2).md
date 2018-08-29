* # 问题分析
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

如果你最多只允许完成一笔交易（即买入和卖出一支股票），设计一个算法来计算你所能获取的最大利润。

注意你不能在买入股票前卖出股票。
* # 编程实现
```c
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int maxProfit = 0;  
        for(int i = 1; i < prices.size(); i++)
        { 
              
             maxProfit += max(0,prices[i]-prices[i-1]);
        }  
        return maxProfit;  
    }
};
```
```python
class Solution:
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        maxProfit = 0
        for i in range(1,len(prices)):
            
            maxProfit += max(0,prices[i]-prices[i-1])
        
        return maxProfit
                        
```
* # 总结体会
  每当prices[i]-prices[i-1]>0的情况，都叠加给maxProfit。
