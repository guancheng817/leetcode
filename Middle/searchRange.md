* # 问题分析
Given an array of integers nums sorted in ascending order, find the starting and ending position of a given target value.

Your algorithm's runtime complexity must be in the order of O(log n).

If the target is not found in the array, return [-1, -1].


给定一个按照升序排列的整数数组 nums，和一个目标值 target。找出给定目标值在数组中的开始位置和结束位置。

你的算法时间复杂度必须是 O(log n) 级别。

如果数组中不存在目标值，返回 [-1, -1]。
* # 编程实现
```c
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        if(nums.empty())
            return {-1,-1};
        int first=findFirst(nums,target);
        int last=findLast(nums,target);
        return {first,last};
    }
    
    int findFirst(vector<int>& nums, int target){
        int left=0,right=nums.size()-1;
        while(left<=right){
            int mid=(left+right)/2;
            if(nums[mid]<target)
                left=mid+1;
            else
                right=mid-1;
        }
        if(left<nums.size()&&nums[left]==target)
            return left;
        return -1;
    }
    int findLast(vector<int>& nums, int target){
        int left=0,right=nums.size()-1;
        while(left<=right){
            int mid=(left+right)/2;
            if(nums[mid]<=target)
                left=mid+1;
            else
                right=mid-1;
        }
        if(right>=0&&nums[right]==target)
            return right;
        return -1;
    }
};
```
* # 总计体会 
利用二分查找，寻找首位置，如果数组中点的值小于target，则在中点值之后的数组查找
如果数组中点值大于或等于target，说明前面数组中可能有target，继续在中点值之前的数组查找，最后当首位置大于末位置时，首位置即为数组中第一个大于或等于target的值，如果首位置上的数与target相等，返回该位置，否则返回-1。同理可找到末位置。
若首位置上的数与target相等，则返回该位置，否则返回-1