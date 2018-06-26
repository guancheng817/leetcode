* # 问题分析
Given a string, find the length of the longest substring without repeating characters.

给定一个字符串，找出不含有重复字符的最长子串的长度。

* # 编程实现
```c
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
            int sum = 0;            
            set<char> setChars;
            for (int i = 0; i < s.size(); ++i) {
                for (int j = i; j < s.size(); ++j) {
                    if (setChars.count(s[j])) {
                        break;
                    } 
                    else {
                        setChars.insert(s[j]);
                    }
                }

                if (setChars.size() > sum) {
                    sum = setChars.size();
                }
                setChars.clear();
            }
       

        return sum;
      
    }
};
```

* # 总结体会
 用两层for循环，外层是字串的起点，内层是字串的终点。
 用set容器保存已经添加的字串的每个字符，用count函数判断是否字符重复出现。
