* # 问题分析
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

如果你最多只允许完成一笔交易（即买入和卖出一支股票），设计一个算法来计算你所能获取的最大利润。

注意你不能在买入股票前卖出股票。
* # 编程实现
```c
class Solution {
public:
    int maxProfit(vector<int>& prices) {
       int index;  
        int maxProfit = 0;  
        for(int i = 0; i < prices.size(); i++)
        { 
              
            for(int j=i+1;j < prices.size();j++)
            {  
                index = prices[j] - prices[i]; 
                if(index>0 && index>maxProfit)
                maxProfit = index;
                     
            }  
        }  
        return maxProfit;   
    }
};
```
* # 总结体会
  这个解法比较简单，但算法复杂度为O（n^2）,耗时较久。