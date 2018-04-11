* # 问题分析
给定一个字符串，确定它是否是回文，只考虑字母数字字符和忽略大小写。
* # 编程实现
```c
class Solution {
public:
    bool isPalindrome(string s) {
        if(s.length()==0)  
        return true;  
    transform(s.begin(), s.end(), s.begin(), ::tolower);  
    int first=0;  
    int last=s.length()-1;  
    for(;first<last;first++,last--)
    {  
        while(first<last&&!isCharOrNumber(s[first]))  
            first++;  
        while(first<last&&!isCharOrNumber(s[last]))  
            last--;  
        if(first<last && s[first]!= s[last])  
            return false;                
    }  
    return true;  
    }
    
    bool isCharOrNumber(char s)
    {  
    if((s>='a'&&s<='z')||(s>='0'&&s<='9'))  
        return true;  
    return false;  
    } 
};
```
* # 总结体会
用C++ stl中 transform先将字符串转为小写，然后从两端开始一一比较；
