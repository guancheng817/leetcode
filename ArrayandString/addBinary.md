## question

给定两个二进制字符串，返回他们的和（用二进制表示）。

输入为非空字符串且只包含数字 1 和 0。
## code
```python
class Solution:
    def addBinary(self, a: str, b: str) -> str:
        l1 = len(a)
        l2 = len(b)
        l = []
        c = 0
        max_l = max(l1, l2)
        if l1 > l2:
            b = b.zfill(l1)
        elif l1 < l2:
            a = a.zfill(l2)

        for i in range(max_l):
            res = int(a[max_l - i - 1]) + int(b[max_l - i - 1]) + c
            res = str(res)
            if res == '2':
                l.append('0')
                c = 1
            elif res == '3':
                l.append('1')
                c = 1
            else:
                l.append(res)
                c = 0
        l.reverse()        
        st  = ''.join(l)
        if c == 1:
            return '1' + st
        else:
            return st
```

## analysis
	
