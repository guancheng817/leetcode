* # 问题分析
给定一个非负整数 numRows，生成杨辉三角的前 numRows 行。

* # 编程实现
```c
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        
        vector<int> column;
        vector<vector<int>> arr(numRows,column);       
        for(int i = 0;i < numRows;i++)
        {
            arr[i].push_back(1);            
            for(int j = 1;j <= i-1;j++)
            {
                arr[i].push_back(arr[i-1][j]+arr[i-1][j-1]);
            }
            if(i > 0)
            {
                arr[i].push_back(1);
            }
            
        }      
        return arr;
        
    }  
};
```
* # 总结体会
  核心在于arr[i-1][j]+arr[i-1][j-1]，下一行的元素除了首尾之外，就是将上一行相邻的两元素相加。