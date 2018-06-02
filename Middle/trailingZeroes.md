* # 问题分析
Given an integer n, return the number of trailing zeroes in n!.

给定一个整数 n，返回 n! 结果尾数中零的数量。
* # 编程实现

```c
class Solution {
public:
    int trailingZeroes(int n) {
        int sum = 0;
            while(n){
                sum += n/5;
                n /=5;
            }
        return sum;
    }
};
```

* # 总结体会
要求得阶乘后0得个数，其实也就是要找乘数中10的个数，可以把10分解为2和5，可以知道2的倍数的数肯定是多于5的倍数的数，所以此题就是要求出5的个数。但是如25,125这样的数，不只含有一个5。