* # 问题分析
A robot is located at the top-left corner of a m x n grid (marked 'Start' in the diagram below).

The robot can only move either down or right at any point in time. The robot is trying to reach the bottom-right corner of the grid (marked 'Finish' in the diagram below).

How many possible unique paths are there?
一个机器人位于一个 m x n 网格的左上角 （起始点在下图中标记为“Start” ）。

机器人每次只能向下或者向右移动一步。机器人试图达到网格的右下角（在下图中标记为“Finish”）。

问总共有多少条不同的路径？

* # 编程实现
```c
class Solution {
public:
    int uniquePaths(int m, int n) {
        int arr[m][n];  
        arr[0][0] = 0;  
        for(int i = 0;i<m;i++)  
            arr[i][0] = 1;  
        for(int j = 0;j<n;j++)  
            arr[0][j] = 1;  
        for (int i = 1; i < m; ++i) {
            for (int j = 1; j < n; ++j) {
                arr[i][j] = arr[i - 1][j] + arr[i][j - 1];
            }
        }
        return arr[m-1][n-1];
    }
};
```
```python
class Solution:
    def uniquePaths(self, m, n):
        """
        :type m: int
        :type n: int
        :rtype: int
        """
        import numpy
        dp = [[0]*n for i in range(m)]
        for i in range(m):
            dp[i][0] = 1
        for i in range(n):
            dp[0][i] = 1      
        for i in range(1,m):
            for j in range(1,n):
                dp[i][j] = dp[i-1][j]+dp[i][j-1]
        
        return dp[m-1][n-1]
```

* # 总结体会
  到（i，j）位置只能从上面或者左边走到，所以有如下关系arr[i][j] = arr[i - 1][j] + arr[i][j - 1];
