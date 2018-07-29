* # 问题分析
假设你正在爬楼梯。需要 n 步你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？
* # 编程实现
```c
class Solution {
public:
    vector<int> res;
    int  climbStairs(int n) {
    
        if (n == 0) 
        {  
            return 0;  
        }  
          
        if (n == 1) 
        {  
            return 1;  
        }  
          
        if (n == 2) 
        {  
            return 2;  
        }  
          
        if (res.size() >= (n-2)) 
        {  
            return res.at(n - 3);  
        }  
          
        res.push_back(climbStairs(n - 1) + climbStairs(n - 2));  
        return res.back();  
    }
};
```
```python
class Solution:
    def climbStairs(self, n):
        """
        :type n: int
        :rtype: int
        """
        if n==0:
            return 0
        if n==1:
            return 1
        if n==2:
            return 2
        l1 = [0,1,2]
        
        for i in range(3,n+1):
            l1.append(l1[i-1]+l1[i-2])
        return l1.pop()
```
* # 总结体会
 一开始直接用递归的方法，但是超时了，原因是重复算了很多遍，于是用一个数组保存中间值，这样就可以减少运算量。
