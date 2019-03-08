### 问题描述
给定一个未排序的整数数组，找出最长连续序列的长度。

要求算法的时间复杂度为 O(n)。
### 代码

```c
class Solution {
public:
    int longestConsecutive(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        int len = nums.size();
        int flag = 1,max = 1;
        if (len == 0) return 0;
        else if (len == 1) return 1;
        
        for(int i = 0; i < len-1; i++){
            if (nums[i+1] == nums[i]) 
                continue;
            if(nums[i+1] - nums[i] == 1){
                flag++;
                max = max > flag? max:flag; 
                continue;
            }
            else {
                max = max > flag? max:flag;
                flag = 1;  
            }
        }     
        return max;
    }
};
```
