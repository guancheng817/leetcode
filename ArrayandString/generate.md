## question 

给定一个非负整数 numRows，生成杨辉三角的前 numRows 行。
## code 

```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        if not numRows:
            return []
        l = []
        sub_list = [1]
        l.append(sub_list)
        for i in range(numRows - 1):
            tmp_list = []
            for j, num in enumerate(sub_list, 0):
                if j == 0:
                    tmp_list.append(1)
                else:
                    tmp_list.append(sub_list[j] + sub_list[j - 1])
                if j == len(sub_list) - 1:
                    tmp_list.append(1)
            l.append(tmp_list)
            sub_list = tmp_list

        

        return l

```

## analysis
注意边界情况
