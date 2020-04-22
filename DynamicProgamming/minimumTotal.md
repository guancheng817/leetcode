## question
给定一个三角形，找出自顶向下的最小路径和。每一步只能移动到下一行中相邻的结点上。

例如，给定三角形：
[
     [2],
    [3,4],
   [6,5,7],
  [4,1,8,3]
]
## code
```python

class Solution:
    def minimumTotal(self, triangle: List[List[int]]) -> int:

        m = len(triangle)
        
        for i in range(1, m):
            for j in range(len(triangle[i])):
                if j==0:
                    triangle[i][j] += triangle[i-1][j]
                elif j == len(triangle[i]) - 1:
                    triangle[i][j] += triangle[i-1][j-1]
                else:
                    triangle[i][j]+=min(triangle[i-1][j-1],triangle[i-1][j])
        
        return min(triangle[-1])
```
## analysis
特判，若triangletriangle为空，返回00，若只有一层len(triangle)==1len(triangle)==1，返回元素。
从第二行开始，遍历区间[1,n)[1,n)：
对每一层的元素进行遍历，遍历区间[0,len(triangle[i]))，存在三种情况：
每一行的首位，triangle[i][j]+=triangle[i-1][j]，等于上一行的相同索引处。
每一行的末位，triangle[i][j]+=triangle[i-1][j-1]，等于上一行的前一位处。
对于其他元素，triangle[i][j]+=min(triangle[i-1][j-1],triangle[i-1][j])，等于上一行中相邻的较小值加上自身。


