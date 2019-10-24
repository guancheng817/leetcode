## question
给定一个含有 M x N 个元素的矩阵（M 行，N 列），请以对角线遍历的顺序返回这个矩阵中的所有元素，对角线遍历如下图所示。先右上角再左下角．

## code
```python
class Solution:
    def findDiagonalOrder(self, matrix: List[List[int]]) -> List[int]:
        if matrix == [[]]:
            return matrix
        l = []
        r, c, k = 0, 0 ,0
        dire = [[-1, 1],[1, -1]]
        m = len(matrix)
        if not m :
            return []
        n = len(matrix[0])
        if not n :
            return []

        for i in range(m*n):
            l.append(matrix[r][c])
            r += dire[k][0]
            c += dire[k][1]

            if r >= m:
                r = m -1
                c = c + 2
                k = 1 - k
            if c >= n:
                c = n -1
                r = r + 2
                k = 1 -k
            if r < 0:
                r = 0
                k = 1 -k
            
            if c < 0:
                c = 0
                k = 1 - k
        return l
                    
```
## analysis
