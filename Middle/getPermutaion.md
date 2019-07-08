### 问题分析
给出集合 [1,2,3,…,n]，其所有元素共有 n! 种排列。

按大小顺序列出所有排列情况，并一一标记，当 n = 3 时, 所有排列如下：

"123"
"132"
"213"
"231"
"312"
"321"
给定 n 和 k，返回第 k 个排列。

示例 1:

输入: n = 3, k = 3
输出: "213"

### 代码

```python
class Solution:
    def getPermutation(self, n: int, k: int) -> str:
        for i,per_list in enumerate(itertools.permutations([i+1 for i in range(n)])):
            if i == k-1:
                return ''.join(str(i) for i in per_list)
```

