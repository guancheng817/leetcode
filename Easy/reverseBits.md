* # 问题分析
颠倒给定的 32 位无符号整数的二进制位。

* # 编程实现
```c
class Solution {
public:
    uint32_t reverseBits(uint32_t n) {
        int i,l;
        vector<int> s;
        
        while (n)
        {
            s.push_back(n & 1);
            n = n>> 1;
        }
     
        int sum = 0;
        l = s.size();
        for (i = 0 ; i <l; ++i)
        {
            sum = sum + s[i] * (1 << (32 - i - 1));
        }

        return sum;
    }
};
```
* # 总结体会
   比较简单的一道题。