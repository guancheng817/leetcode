* # 问题分析
Given an array of size n, find the majority element. The majority element is the element that appears more than ? n/2 ? times.

You may assume that the array is non-empty and the majority element always exist in the array.

给定一个大小为 n 的数组，找到其中的众数。众数是指在数组中出现次数大于 ? n/2 ? 的元素。

你可以假设数组是非空的，并且给定的数组总是存在众数。

* # 编程实现
```c
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        map<int,int> m;
        int l = nums.size();
        for(int i=0;i<l;i++){
            m[nums[i]]++;
        }
        
        for(int i=0;i<l;i++){
             if(m[nums[i]]>l/2)
                 return nums[i];
        }
        
    }
};
```
* # 总结体会
   遍历数组，用map记录每个数出现的次数，再次遍历后找出。