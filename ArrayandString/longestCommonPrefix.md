## question

编写一个函数来查找字符串数组中的最长公共前缀。

如果不存在公共前缀，返回空字符串 ""。

## code
```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:

        prefix = ''

        l = len(strs)
        if l == 0:
            return ""
        elif l == 1:
            return strs[0]
        l1 = len(strs[0])

        for j in range(l1):
            for i in range(l - 1):
                if j > len(strs[i]) -1  or j> len(strs[i+1]) - 1:
                    return prefix
                if strs[i][j] != strs[i + 1][j]:
                    return prefix
                if i == l - 2:
                    prefix += strs[i][j]
        
        return prefix
```


## analysis
