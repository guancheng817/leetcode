* # 问题分析
写一个程序，输出从 1 到 n 数字的字符串表示。

1. 如果 n 是3的倍数，输出“Fizz”；

2. 如果 n 是5的倍数，输出“Buzz”；

3.如果 n 同时是3和5的倍数，输出 “FizzBuzz”。
* # 编程实现
```c
class Solution {
public:
    vector<string> fizzBuzz(int n) {
        int i;
        vector<string> s;
        if(n<0)
        {
            return s;
        }
        for(int i=1;i<=n;i++)
        {
            if(i%3==0&&i%5==0)
            
                s.push_back("FizzBuzz");
            
            else if(i%3==0)
            
                s.push_back("Fizz");
            
            else if(i%5==0)
            
                s.push_back("Buzz");
            
            else          
                s.push_back(to_string(i));          
        }
        return s;
    }
};
```
* # 总结体会
  简单的数学问题。