## question


## code
```python

class Solution:
    def reverseWords(self, s: str) -> str:

        s = s.strip()
        data = s.split()
        l = len(data)
        re = ""
        for i in range(l):
            re = re + data[l-i-1]+" "
        return re.strip()

		
```

## analysis
很python的解法
```python
 return " ".join(s.split()[::-1])
```
