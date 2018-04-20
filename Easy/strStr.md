* # 问题分析
Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.<br/>
给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。

* # 编程实现
```c
class Solution {
public:
    int strStr(string haystack, string needle) {
    
        if(needle == " ") 
          return 0;  
        int l1=haystack.size();
        int l2=needle.size();
        
        if(l1 < l2) return -1;  
        
        for(int i = 0;i < l1-l2+1;i++)
        {  
            
            if(haystack.substr(i,l2) == needle)  
                return i;  
        }  
        return -1;  
    }
};
```

* # 总结体会
  直接运用String中的substr（）函数，可以快速解出此题。