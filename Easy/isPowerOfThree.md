* # 问题分析
给出一个整数，写一个函数来确定这个数是不是3的一个幂
* # 编程实现
```c
method 1:
class Solution {
public:
    bool isPowerOfThree(int n) {
     while(n&&n%3==0)
        {
            n/=3;
        }
        if(n==1)
            return true;
        else 
            return false;
    }
};
method 2
class Solution {
public:
    bool isPowerOfThree(int n) {
        if(n<=0)
            return false;
        int k=log(INT_MAX)/log(3);
        int b3=pow(3,k);
        if(b3%n==0)
            return true;
        else 
            return false;
    }
};
```
* # 总结体会
  法一用循环的方式，法二不用循环，找出int范围内3的幂最大整数，这个整数必然可以被n整除。