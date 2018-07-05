 * # 问题分析
 
 Given a 32-bit signed integer, reverse digits of an integer.
  
  
给定一个 32 位有符号整数，将整数中的数字进行反转。


* # 编程实现

```c

class Solution {
public:
    int reverse(int x) {
        long long res=0;
        int sign = 1;
        if (x > 0){ 
            sign = -1; 
            x = abs(x);
        }
        while (x > 0) {
            res = res * 10 + x % 10;
            x /= 10;
        }
 
        if (res > INT_MAX) 
            res = 0;
        return res*sign;

    }
};
```

* # 总结体会
  
先判断正负，若是负数，将其转化为正数进行处理，在将整数各位逐个反转。
上次没有处理好溢出问题，导致有几个点没有通过，本次改正。