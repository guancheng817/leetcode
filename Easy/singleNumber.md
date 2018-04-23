* # 问题分析
Given an array of integers, every element appears twice except for one. Find that single one.
Note:
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

题意 ： 给定一个整数数组，除了一个元素外，每个元素都会出现两次。找到那一个。           

注：   你的算法应该有一个线性运行时复杂性。你可以不使用额外的内存来实现它吗？

* # 编程实现
```c
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int  sign=0;
        for(int i=0;i<nums.size();i++)
        {
            sign ^= nums[i];
        }
        
        return sign;
    }
};
```
* # 总结体会
 其实，第一反应是用空间换时间，用哈希来算，但题目后面有要求，不用额外的内存，
 因为0与任何数的异或都是去其本身，所以最后采用异或的方式来求解。
};