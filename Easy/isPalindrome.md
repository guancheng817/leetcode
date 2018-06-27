* # 问题分析
给定一个字符串，确定它是否是回文，只考虑字母数字字符和忽略大小写。
* # 编程实现
```c
class Solution {
public:

        bool isPalindrome(string s) {
        if(s.size()==0)  
        return true;  
    int first=0;  
    int last=s.length()-1;  
    while(first<last)
    {  
        while(first<last&&!isCharOrNumber(s[first]))  
            first++;  
        while(first<last&&!isCharOrNumber(s[last]))  
            last--;  
        if(tolower(s[first])!= tolower(s[last])) 
            return false;  
        
            first++;
            last--;
    }  
    return true; 

    }
    
    bool isCharOrNumber(char s)
    {  
    if((s>='a'&&s<='z')||(s>='0'&&s<='9')||(s>='A'&&s<='Z'))  
        return true;  
    return false;  
    
    }
};
```
* # 总结体会
 根据回文串的定义，从第一个字符到最后一个字符一一比较，若相等，则为回文串。用tolower函数将字母全转化为小写来进行比较。
