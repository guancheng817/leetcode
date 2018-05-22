* # 问题描述
请编写一个函数，其功能是将输入的字符串反转过来
* # 代码实现
```c
class Solution {
public:
    string reverseString(string s) {
         int len=s.size();
        if(len==0||s.empty())
        {
            return "";
        }
        int left=0,right=len-1;
        for(;left<right;left++,right--)
        {
            char tmp=s[left];
            s[left]=s[right];
            s[right]=tmp;
        }
        return s;
    }
};
```
* # 总结体会
 上此编写的代码，有几个测试无法通过，这次进行编写。设置左右两个指针，从串头，串尾向中间逼近。
