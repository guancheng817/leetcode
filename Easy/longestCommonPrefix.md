* # 问题分析
编写一个函数来查找字符串数组中的最长公共前缀。
* # 编程实现
```c
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
     if(strs.size()==0)
         return "";
     int j,i;
     string prefix="";
     for(i=0;i<strs[0].size();i++)
     {
         for(j=0;j<strs.size();j++)
             if(strs[0][j]!=strs[j][i])
                 return prefix;
         prefix=prefix+strs[0][i];
     }
     return prefix;
    }
};
```
* # 总结体会
  运用c++中的string类，将字符串数组中的第一个字符串，与剩下的字符串进行一个纵向比较。
  即依次用第一个字符串中的每一个字母与余下的字符串中的每一个字符相比较，若无相同，直接返回
  prefix，否则将相同的字母加到prefix字符串中。
