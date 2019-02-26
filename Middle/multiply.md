## 问题分析
给定两个以字符串形式表示的非负整数 num1 和 num2，返回 num1 和 num2 的乘积，它们的乘积也表示为字符串形式。

##  代码
```c
class Solution {
public:
    string multiply(string str1, string str2) {
        
    if (str1 == "0" || str2 == "0")
        return "0";
    int size1 = str1.size(), size2 = str2.size();
    string str(size1 + size2,'0');
    for (int i = size2 - 1; i >= 0; --i) {
        int mulflag = 0, addflag = 0;
        for(int j = size1 - 1; j >= 0; --j) {
            int temp1 = (str2[i] - '0') * (str1[j] - '0') + mulflag;
            mulflag = temp1 / 10;
            temp1 = temp1 % 10;
            int temp2 = str[i + j + 1] - '0' + temp1 + addflag;
            str[i + j + 1] = temp2 % 10 + '0';
            addflag = temp2 / 10;
        }
        str[i] += mulflag + addflag;
    }
    if (str[0] == '0')
        str = str.substr(1, str.size());
    
     return str;
    }
};
```