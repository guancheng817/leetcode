* # 问题分析
Given an array with n objects colored red, white or blue, sort them in-place so that objects of the same color are adjacent, with the colors in the order red, white and blue.

Here, we will use the integers 0, 1, and 2 to represent the color red, white, and blue respectively.
给定一个包含红色、白色和蓝色，一共 n 个元素的数组，原地对它们进行排序，使得相同颜色的元素相邻，并按照红色、白色、蓝色顺序排列。

此题中，我们使用整数 0、 1 和 2 分别表示红色、白色和蓝色。
* # 编程实现
```c
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int count[3]={0};
        for(int i=0;i<nums.size();i++){
            if(nums[i]>=0 && nums[i]<=2)
                count[nums[i]]++;
        }
        
         int index = 0;
        for(int i=0;i<count[0];i++)
             nums[index++]=0;
        for(int i=0;i<count[1];i++)
             nums[index++]=1;
        for(int i=0;i<count[2];i++)
             nums[index++]=2;
    }
};
```
* # 总结体会
 第一次扫描数组，用count数组记录每个颜色的个数，第二次扫描对颜色排序。