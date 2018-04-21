 * # 问题分析
  Given a 32-bit signed integer, reverse digits of an integer.
  
  给定一个 32 位有符号整数，将整数中的数字进行反转。

* # 编程实现
```c
class Solution {
public:
    int reverse(int x) {
        int reverse=0;  
        int temp;    
        int sign=1;  
        if (x<0)//如果x小于0，将它变成正的  
        {  
            sign=-1;  
            x=abs(x);  
        }  
        
        while(x)
        {             
                temp=x%10;  
                reverse=reverse*10+temp;  
                x=x/10;                                 
        } 


          return reverse*sign;  
    }
};
```
* # 总结体会
  先判断正负，若是负数，将其转化为正数进行处理，在将整数各位逐个反转。