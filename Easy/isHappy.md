* # 问题分析

Write an algorithm to determine if a number is "happy".

A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

编写一个算法来判断一个数是不是“快乐数”。

一个“快乐数”定义为：对于一个正整数，每一次将该数替换为它每个位置上的数字的平方和，然后重复这个过程直到这个数变为 1，也可能是无限循环但始终变不到 1。如果可以变为 1，那么这个数就是快乐数。
* # 编程实现
```c
class Solution {
public:
bool isHappy(int n) {  
         
        set<int> s;  
        while(1) {  
            if(n == 1) return true;  
            if(s.count(n) == 1) return false;  
            s.insert(n);  
            n = happyNumber(n);  
        }  
    }  
      
    int happyNumber(int n) {  
        int sum = 0;  
        while(n!= 0) {  
            sum += (n%10)*(n%10);  
            n /= 10;  
        }  
        
        return sum;  
    }  
};
```
* # 总结体会
 用一个set容器来判断出现的数之前是否出现过，如果出现过则出现无限循环，即不是快乐数。