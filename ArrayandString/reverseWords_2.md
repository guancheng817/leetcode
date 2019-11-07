## question
给定一个字符串，你需要反转字符串中每个单词的字符顺序，同时仍保留空格和单词的初始顺序。

输入: "Let's take LeetCode contest"
输出: "s'teL ekat edoCteeL tsetnoc" 
## code
```python
class Solution:
    def reverseWords(self, s: str) -> str:

        str_l = s.split()
        re = ""
        for i in str_l:
            re = re + i[::-1]+" "

        return re.rstrip()
```

## analysis
另一种解法
```python
return ' '.join(s.split()[::-1])[::-1]
```
