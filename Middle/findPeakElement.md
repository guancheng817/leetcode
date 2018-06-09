* # 问题分析
A peak element is an element that is greater than its neighbors.

Given an input array nums, where nums[i] ≠ nums[i+1], find a peak element and return its index.

The array may contain multiple peaks, in that case return the index to any one of the peaks is fine.
峰值元素是指其值大于左右相邻值的元素。

给定一个输入数组 nums，其中 nums[i] ≠ nums[i+1]，找到峰值元素并返回其索引。

数组可能包含多个峰值，在这种情况下，返回任何一个峰值所在位置即可。

你可以假设 nums[-1] = nums[n] = -∞。
You may imagine that nums[-1] = nums[n] = -∞.
* # 编程实现
```c
class Solution {
public:
    int findPeakElement(vector<int>& nums) {

          
        int left = 0;  
        int right = nums.size() - 1;  
          
        while(left <= right)  
        {  
            if(left == right) return left;  
              
            int mid = left + (right - left) / 2;  
              
            if(nums[mid] < nums[mid+1])  
            {  
                left = mid + 1;  
            }  
            else  
            {  
                right = mid;  
            }  
        }  
    }
};
```

* # 总结体会
 要实现O(logN)，用二分查找，如果nums[mid] > nums[mid+1]，则在mid之前存在峰值元素，如果nums[mid] < nums[mid+1]，则在mid+1之后存在峰值元素。

