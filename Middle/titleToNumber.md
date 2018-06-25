* # 问题分析
Given a column title as appear in an Excel sheet, return its corresponding column number.

给定一个Excel表格中的列名称，返回其相应的列序号。
* # 编程实现
```c
class Solution {
public:
    int titleToNumber(string s) {
        int l = s.size();
        int sum = 0;
        int tmp = 1;
        while(l){        
            sum = sum + (s[l-1]-'A'+1)*tmp;
            tmp = tmp * 26;
            l--;
        }
        return sum;
    }
};
```

* # 总结体会
表格的列名称是26进制，序列号是十进制，将26进制转化为10进制。