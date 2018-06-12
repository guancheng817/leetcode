* # 问题分析

Given an array of non-negative integers, you are initially positioned at the first index of the array.

Each element in the array represents your maximum jump length at that position.

Determine if you are able to reach the last index.
给定一个非负整数数组，你最初位于数组的第一个位置。

数组中的每个元素代表你在该位置可以跳跃的最大长度。

判断你是否能够到达最后一个位置。

* # 编程实现
```c
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int loc=0;
        int i=0;
        
        for(int i=0;i<nums.size() && i<=loc;i++){
            loc=max(loc,i+nums[i]);
        }
        return loc>=nums.size()-1;
    }
};
```
* # 总结体会
 判断能否跳到终点，在遍历数组的过程中，更新每个点能跳到最远的范围，如果最后这个范围大于等于终点，那么就能跳到。
