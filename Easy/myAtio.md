 * # 问题分析
 Implement atoi which converts a string to an integer.

The function first discards as many whitespace characters as necessary until the first non-whitespace character is found. Then, starting from this character, takes an optional initial plus or minus sign followed by as many numerical digits as possible, and interprets them as a numerical value.

The string can contain additional characters after those that form the integral number, which are ignored and have no effect on the behavior of this function.

If the first sequence of non-whitespace characters in str is not a valid integral number, or if no such sequence exists because either str is empty or it contains only whitespace characters, no conversion is performed.

If no valid conversion could be performed, a zero value is returned.
实现 atoi，将字符串转为整数。

在找到第一个非空字符之前，需要移除掉字符串中的空格字符。如果第一个非空字符是正号或负号，选取该符号，并将其与后面尽可能多的连续的数字组合起来，这部分字符即为整数的值。如果第一个非空字符是数字，则直接将其与之后连续的数字字符组合起来，形成整数。

字符串可以在形成整数的字符后面包括多余的字符，这些字符可以被忽略，它们对于函数没有影响。

当字符串中的第一个非空字符序列不是个有效的整数；或字符串为空；或字符串仅包含空白字符时，则不进行转换。

若函数不能执行有效的转换，返回 0。
* # 编程实现
```c
class Solution {
public:
    int myAtoi(string str) {
             int i=0,sign=1,num = 0;  
     if(str.size()==0)  
         return 0;  
     while(str[i]==' '&& i<str.size()){  
         i++;  
     }  
     if(str[i]=='+'||str[i]=='-'){  
         sign = str[i]=='+'?1:-1;  
         i++;  
     }  
     while(i<str.size()){  
         int digit= str[i]-'0';  
         if (digit<0||digit>9){  
             break;  
         }  
         if(INT_MAX/10 < num || INT_MAX/10 == num && INT_MAX %10 < digit){  
             return sign == 1 ? INT_MAX : INT_MIN;  
         }  
         num = 10 * num + digit;  
            i ++;  
     }
        return num*sign;
    }
};
```
* # 总结体会
 本题难点在于需要考虑各个方面的情况，解题过程中的也有出现许多考虑不足之处。
};