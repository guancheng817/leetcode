* # 问题分析
统计所有小于非负数整数 n 的质数的数量。
 * 编程实现
 ```c
class Solution {
public:
    int countPrimes(int n) {  
        int count = 0;  
        if(n > 2) 
        count ++;  
        for(int i = 3; i < n; i +=2 )
        {  
            if(isPrime(i))  
                count ++;  
        }  
        return count;  
    }
        
  
       bool isPrime(int n){  
 
    for(int i = 2; i <= sqrt(n); i ++){  
            if(n % i == 0)  
            return false;  
        }  
        return true;  
    }        
};
```
* 总结体会
  设k为n的一个约数，若n%k==0；那么由k*(n/k)==n可知，k与n/k必有一个小于等于sqrt（n），而另一个则大等于，
  所以只需判断n能否被2，3，，，sqrt（n）整除，即可判断是否为素数。