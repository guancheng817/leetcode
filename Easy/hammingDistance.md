* # 问题分析
两个整数之间的汉明距离指的是这两个数字对应二进制位不同的位置的数目。

给出两个整数 x 和 y，计算它们之间的汉明距离。
 * 编程实现
 ```c
class Solution {
public:
    int hammingDistance(int x, int y) {
        int i,l,sum=0;
        vector<int> s1;
        vector<int> s2;
        while(x||y)
        {
            s1.push_back(x%2);
            s2.push_back(y%2);
            x= x/2;
            y= y/2;
        }
        l=max(s1.size(),s2.size());
        for(i=0;i<l;i++)
        {
            if(s1[i] != s2[i])
                sum++;
        }
        
        return sum;
    }
};
```
* 总结体会
   在上一题求汉明重量进行拓展，计算汉明距离。