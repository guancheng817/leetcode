## question

给定一个非空字符串 s 和一个包含非空单词列表的字典 wordDict，判定 s 是否可以被空格拆分为一个或多个在字典中出现的单词

说明：

拆分时可以重复使用字典中的单词。
你可以假设字典中没有重复的单词。

## code


```python

class Solution:
    def wordBreak(self, s: str, wordDict: List[str]) -> bool:       
        n=len(s)
        dp=[False]*(n+1)
        dp[0]=True
        for i in range(n):
            for j in range(i+1,n+1):
                if(dp[i] and (s[i:j] in wordDict)):
                    dp[j]=True
        return dp[-1]

```

## analysis
1. 初始化dp=dp=[False,⋯,False]，长度为n+1。n为字符串长度。dp[i]表示s的前i位是否可以用wordDict中的单词表示
2. 初始化dp[0]=True，空字符可以被表示
3. 遍历字符串的所有子串，遍历开始索引ii，遍历区间[0,n)：
  遍历结束索引jj，遍历区间[i+1,n+1)：
  若dp[i]=True且ss[i,⋯,j)在wordlist中：dp[j]=True。解释：dp[i]=True说明s的前i位可以用wordDict表示，则s[i,⋯,j)出现在wordDict中，说明s的前j位可以表示。





