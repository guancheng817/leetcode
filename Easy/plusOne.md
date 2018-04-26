* # 问题分析

给定一个非负整数组成的非空数组，在该数的基础上加一，返回一个新的数组。

最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。

你可以假设除了整数 0 之外，这个整数不会以零开头。


* # 编程实现
```c
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        int c = 1,i;
        for (int i = digits.size()- 1; i >= 0; i--) {
            if (c == 0) {
                return digits;
            }
            int tmp = digits[i] + c;
            c = tmp / 10;
            digits[i] = tmp % 10;
        }
        
        
        if (c!= 0) {
             vector<int> new1;
            for(i=0;i<digits.size();i++)
            {
                new1.push_back(0);              
            } 
            new1.insert(new1.begin(),1) ;
            return new1;
        }
        return digits;
    }
};
```
* # 总结体会
 本题关键在与对进位后的处理，若要使最高为进位，则所有低位的数字必须使9.
