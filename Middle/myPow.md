* # 问题分析
Implement pow(x, n), which calculates x raised to the power n(x^n).

实现 pow(x, n) ，即计算 x 的 n 次幂函数。
* # 编程实现

```c
class Solution {
public:
    double myPow(double x, int n) {
        if (n < 0) return 1 / power(x, -n);
        return power(x, n);
    }
    double power(double x, int n) {
        if (n == 0) return 1;
        double half = power(x, n / 2);
        if (n % 2 == 0) return half * half;
        return x * half * half;
    }
    
};
```

* # 总结体会
通过递归用二分计算，把n缩小到0，因为任何数的0次方都为1，再往回乘，若n为偶数，把上次递归得到的值求平方后返回，若是奇数，再乘个x的值。若n为负数，取其绝对值计算，再求其倒数。