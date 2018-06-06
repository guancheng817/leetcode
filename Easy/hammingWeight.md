* # 问题分析

编写一个函数，输入是一个无符号整数，返回其二进制表达式中数字位数为 ‘1’ 的个数（也被称为汉明重量）。

* # 编程实现
```c

class Solution {
public:
    int hammingWeight(uint32_t n) {
        int i,l,sum=0;
        vector<int> s;
        while(n)
        {
            s.push_back(n%2);
            n= n/2;
        }
        l = s.size();
        for(l-1;l>0;l--)
        {
            if(s[l-1]==1)
                sum++;
        }
        
        return sum;
    }
};

```



```c

class Solution {
public:
    int hammingWeight(uint32_t n) {
        int count = 0;
        
        uint32_t flag = 1;
        
        while(flag){
            if(n & flag) {
               count ++;
            }
            flag = flag << 1;
        }
        
        return count;
    }
};
```


* # 总结体会
 
将无符号整数化作二进制数，将二进制数存入vector<int>，然后统计其1的个数。上次解法运行时间过长，不够简洁。这次用位运算来解，通过与flag逐位相与，代码更加简洁。