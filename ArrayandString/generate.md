## question 

给定一个非负整数 numRows，生成杨辉三角的前 numRows 行。
## code 

```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        if not numRows:
            return []
        
        l = [[1]]
        
        for i in range(1, numRows):
            sub_list = []
            for j in range(len(l[i-1])):
                if j == 0:
                    sub_list.append(1)
                else:
                    sub_list.append(l[i-1][j] + l[i-1][j-1])
            
            sub_list.append(1)
            l.append(sub_list)
            
        return l

```

## analysis
注意边界情况
