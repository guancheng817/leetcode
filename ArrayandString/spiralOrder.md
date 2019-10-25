## question

给定一个包含 m x n 个元素的矩阵（m 行, n 列），请按照顺时针螺旋顺序，返回矩阵中的所有元素。

## code

class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        l = []
        r, c, k, index = 0, 0, 0, 0
        direc = [(0, 1), (1, 0), (0, -1), (-1, 0)]
        m = len(matrix)
        if not m:
            return []
        n = len(matrix[0])
        if not n:
            return []

        for i in range(m * n):
            l.append(matrix[r][c])

            r += direc[k][0]
            c += direc[k][1]

            if c >= n - index:
                c = n - index - 1
                r += 1
                k += 1
                k %= 4
            elif r >= m - index:
                r = m - index - 1
                c -= 1
                k += 1
                k %= 4
            elif c < index:
                c += 1
                r -= 1
                k += 1
                k %= 4
            elif r == index and c == index:
                c += 1
                r += 1
                k +=1
                if k == 4:
                    index += 1
                k %= 4

        return l
## analysis

注意边界情况
