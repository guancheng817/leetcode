* # 问题描述
给定一个有序数组，你需要原地删除其中的重复内容，使每个元素只出现一次,并返回新的长度。

不要另外定义一个数组，您必须通过用 O(1) 额外内存原地修改输入的数组来做到这一点。
* # 编程实现
```c
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        if (nums.size() == 0)  
           return 0;    
        int n = 0; 
        for (int i=0; i < nums.size() ; i++)
        {  
            if ( nums[i] != nums[n] ) 
            {  
                n++;  
                nums[n] = nums[i];  
            }  
        }  
        n+=1;   
        return n;  
    }
};
```
* # 总结体会
首先这是一个有序数组，
若i位置的数字等于n位置的数字，则该数字重复出现，不执行if语句；
若i位置的数字不等于n位置的数字，则该数字不重复，然后放到i的下一位置，最后使n加1，
然后返回n，即为新的数组长度

