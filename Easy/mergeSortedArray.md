* # 问题分析
Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

给定两个有序整数数组 nums1 和 nums2，将 nums2 合并到 nums1中，使得 num1 成为一个有序数组。

* #编程实现
```c
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {

        int index = m + n - 1;
        m--,n--;
        while (m >= 0 && n >= 0) 
        {
            if(nums1[m]>nums2[n])
                nums1[index--]=nums1[m--];
            else
                nums1[index--]=nums2[n--];
        
        }
        while (n >= 0) nums1[index--] = nums2[index--];
    }
};
```
* # 总结体会
 将两个有序数组，从最后一个数开始比较大小，然后依次从后往前推进，若最后当nums1数组循环完之后，num2数组还没插入num1数组中，再进行一个循环，将num2数组中
 的数覆盖掉num1数组中前面的数。
