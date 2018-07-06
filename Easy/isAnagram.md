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
        vector<int> v1(26);
        vector<int> v2(26);
        if(s.size()!=t.size())
            return false;
        for(int i=0;i<s.size();i++)
        {
            m1[s[i]-'a']++;
            m2[t[i]-'a']++;
        }
        for(int i=0;i<26;i++)
        {
            if(m1[i]!=m2[i])
                return false;
        }
        
        return true;
    }
};
```
```c
class Solution {
public:
    bool isAnagram(string s, string t) {
       vector<int> vec(26);
      for(auto c:s){
        vec[c-'a']++;
     }
     for(auto c:t){
         vec[c-'a']--;
     }
     for(int i=0;i<26;i++){
         if(vec[i]!=0)
             return false;
     }
        
        return true;
    }
};
```
* # 总结体会
 建两个映射表，分别统计每个字符串中，每个字母的个数，若两个字符串中每个字母个数不同，则返回false；
否则返回true。
第二种方法，先统计第一个字符串每个字母的个数，然后操作第二个字符串将每个字母的个数逐一减去，若最后不为0，则返回false。