* # 问题分析
给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的一个字母异位词。
Given two strings s and t, write a function to determine if t is an anagram of s.

For example,
s = "anagram", t = "nagaram", return true.
s = "rat", t = "car", return false.
* # 编程实现
```c
class Solution {
public:
    bool isAnagram(string s, string t) {
        unordered_map<int,int> m1;
        unordered_map<int,int> m2;
        if(s.size()!=t.size())
            return false;
        for(int i=0;i<s.size();i++)
        {
            m1[s[i]]++;
            m2[t[i]]++;
        }
        for(int i=90;i<130;i++)
        {
            if(m1[i]!=m2[i])
                return false;
        }
        
        return true;
    }
};
```
* # 总结体会
 建两个映射表，分别统计每个字符串中，每个字母的个数，若两个字符串中每个字母个数不同，则返回false；
否则返回true。