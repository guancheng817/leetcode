* # 问题分析
Given a string s, find the longest palindromic substring in s. You may assume that the maximum length of s is 1000.
* # 编程实现
```python
class Solution:
    def longestPalindrome(self, s):

        l = len(s)
        maxl = 0
        start = 0
        for i in range(l):
            if i - maxl >= 1 and s[i-maxl-1: i+1] == s[i-maxl-1: i+1][::-1]:
                start = i - maxl - 1
                maxl += 2
                continue
            if i - maxl >= 0 and s[i-maxl: i+1] == s[i-maxl: i+1][::-1]:
                start = i - maxl
                maxl += 1
        return s[start: start + maxl]
```

* # 总结体会
用动态规划的思想，dp[i,j]表示第i个字符到第j个字符的回文子串数，所以有关系式， 当s[i]=s[j]，dp[i,j]=dp[i+1,j−1]+2，当s[i]!=s[j]时，dp[i,j]=max(dp[i+1,j],dp[i,j−1])。
