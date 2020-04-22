## question

给定一个字符串 s，找到 s 中最长的回文子串。你可以假设 s 的最大长度为 1000。
## code
```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        n = len(s)
        if n == 1:
            return s[0]
        dp = [[False for _ in range(n)] for _ in range(n)]

        for i in range(n):
            dp[i][i] = True

        max_len = 1
        start = 0
        for j in range(1, n):
            for i in range(0,j):
                if s[i] == s[j]:
                    if j - i < 3:
                        dp[i][j] = True
                    else:
                        dp[i][j] = dp[i+1][j-1]
                else:
                    dp[i][j] = False 

                if dp[i][j]:
                    cur_len = j - i+1
                    if cur_len > max_len:
                        max_len = cur_len
                        start = i
        
        return s[start:start+max_len]
```
## analysis
从回文串的定义展开讨论：

1、如果一个字符串的头尾两个字符都不相等，那么这个字符串一定不是回文串；

2、如果一个字符串的头尾两个字符相等，才有必要继续判断下去。

（1）如果里面的子串是回文，整体就是回文串；

（2）如果里面的子串不是回文串，整体就不是回文串。

即在头尾字符相等的情况下，里面子串的回文性质据定了整个子串的回文性质，这就是状态转移。因此可以把“状态”定义为原字符串的一个子串是否为回文子串。

