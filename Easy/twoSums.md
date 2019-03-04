* # 问题分析
给定一个整数数组和一个目标值，找出数组中和为目标值的两个数。

你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。

 Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.
* # 编程实现
```c
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int len = nums.size(),i,j;
        vector<int> m;
        for(i=0;i<len;i++)
        {
            for(j=i+1;j<len;j++)
            {
                if(nums[i]+nums[j]==target)
                {
                    m.push_back(i);
                    m.push_back(j);
                    return m;
                }
            }
        }
        
        return m;
    }
};  
```



```c
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int,int> m;
        for(int i=0;i<nums.size();i++)
        {
            if(m.count(target-nums[i])){

                return {i,m[target-nums[i]]};
            }
            
            m[nums[i]]=i;
        }
    }
};
```
* # 总结体会
 
此种方法思路简单，两个for嵌套使用，时间复杂度为O（N^2）.
用一个hash表，键为数组元素值，值为数组元素下标，将复杂度降为O(n).
