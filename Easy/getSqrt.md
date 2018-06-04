* # 问题分析
Implement int sqrt(int x).

Compute and return the square root of x, where x is guaranteed to be a non-negative integer.

Since the return type is an integer, the decimal digits are truncated and only the integer part of the result is returned.
实现 int sqrt(int x) 函数。

计算并返回 x 的平方根，其中 x 是非负整数。

由于返回类型是整数，结果只保留整数的部分，小数部分将被舍去。
* # 编程实现
class Solution {
public:
    int mySqrt(int x) {
        if(x<=1)
            return x;
            int left = 1;
            int right = x/2;
        while(1){
            int mid = left + (right-left)/2;

            if(mid > x/mid){
                 right = mid - 1;
            }
            else{
                if(mid + 1 > x/(mid+1))
                    return mid;
                left = mid + 1;
            }
        }
    }
};

* # 总结体会
除了0和1，正整数的平方根一定是在1到x/2之间，所以采用二分法的方法。查找条件为
若mid * mid > x，则right = mid -1；
否则，当(mid+1)*(mid+1)*>x,return mid；
若不满足 ：left = mid+1； 继续二分查找。