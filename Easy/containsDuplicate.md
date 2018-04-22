* # 问题分析
Given an array of integers, find if the array contains any duplicates. 
Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

给定一个整数数组，判断是否存在重复元素。

如果任何值在数组中出现至少两次，函数应该返回 true。如果每个元素都不相同，则返回 false。
* # 编程实现
 ```c 
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        int  i,j;
        unordered_map<int,int>  hash;
        for(i=0;i<nums.size();i++)
            hash[nums[i]]++;
        
        for(j=0;j<nums.size();j++)
        {
            if(hash[nums[j]]>1)
                return true;
        }
        
        return false;
    }
};
```
* # 总结体会
 建一个hash数组，统计每个数组元素出现的次数，若大于1，则返回true；