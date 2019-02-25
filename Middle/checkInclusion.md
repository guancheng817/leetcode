## 问题分析
给定两个字符串 s1 和 s2，写一个函数来判断 s2 是否包含 s1 的排列。

换句话说，第一个字符串的排列之一是第二个字符串的子串。
```c
class Solution {
public:
    bool checkInclusion(string s1, string s2) {
    int len1 = s1.size();
    int len2 = s2.size();
    if (len1 > len2) return false;

    vector<int> maps1(26), maps2(26);
    for (int i = 0; i < len1; ++i)
    {
        maps1[s1[i] - 'a'] ++;
        maps2[s2[i] - 'a'] ++;
    }
    if (maps1 == maps2) return true;

    for (int i = 0; i  < len2-len1; ++i)
    {
        maps2[s2[i] - 'a'] --;
        maps2[s2[i + len1] - 'a'] ++;
        if (maps1 == maps2) return true;
    }
    return false;
    
    }
};
```