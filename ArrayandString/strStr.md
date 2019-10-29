## question


## code

```python

class Solution:
    def strStr(self, haystack: str, needle: str) -> int:

        n1 = len(haystack)
        n2 = len(needle)
        if n2 == 0:
            return 0
        if n1 == 0:
            return -1
        if n1 < n2:
            return -1
        for i in range(n1-n2+1):
            for j in range(n2):
                if haystack[i+j] == needle[j]:
                    pass
                else:
                    break
                if j == n2-1:
                    return i
        return -1

```

## analysis

有个很python的解法
```python

haystack[i:i+len(needle)] == needle
```
