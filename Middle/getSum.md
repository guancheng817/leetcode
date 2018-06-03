* # 问题分析
 Calculate the sum of two integers a and b, but you are not allowed to use the operator + and -.

不使用运算符 + 和-，计算两整数a 、b之和。
* # 编程实现
```c
class Solution {
public:
    int getSum(int a, int b) {
        if(a == 0) return b ;
        if(b == 0) return a ;
        int i = a^b;
        int sum = (a&b)<<1;
        return getSum(sum,i);
    }
};
```
* # 总结体会
 用位运算通过二进制加法的方式来解这道题。
 首先，在二进制中加法中，忽略进位。即将两数进行异或运算。
 其次，只有在1＋1会产生进位，相对于这一数位的进位值为10，而10＝(1&1)<<1。
 最后，将以上两步的结果相加，进行递归，直到不再产生进位。