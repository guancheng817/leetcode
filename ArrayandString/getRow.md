## question
给定一个非负索引 k，其中 k ≤ 33，返回杨辉三角的第 k 行。
## code

```python
class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        if not rowIndex:
            return [1]
        sub_list = [1]
        l.append(sub_list)
        for i in range(rowIndex):
            tmp_list = []
            for j, num in enumerate(sub_list, 0):
                if j == 0:
                    tmp_list.append(1)
                else:
                    tmp_list.append(sub_list[j] + sub_list[j - 1])
                if j == len(sub_list) - 1:
                    tmp_list.append(1)
            sub_list = tmp_list

        return tmp_list
```

## analysis
此题是杨辉三角II,杨辉三角I显示每一层，此题显示第k层，下标从０开始。
