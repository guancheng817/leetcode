* # 问题分析
给定一个数组 nums, 编写一个函数将所有 0 移动到它的末尾，同时保持非零元素的相对顺序。

例如， 定义 nums = [0, 1, 0, 3, 12]，调用函数之后， nums 应为 [1, 3, 12, 0, 0]。

注意事项:
* # 编程实现
```c
void moveZeroes(int* nums, int numsSize) {
    int i=0,n=0;
    for(i;i<numsSize;i++)
    {
        
        if(nums[i]!=0)
        {
            nums[n]=nums[i];
            n++;
        }

    }
    for(n;n<numsSize;n++)
        nums[n]=0;
}
```

```c
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n=0;
        int l = nums.size();
        for(int i=0;i<l;i++){
            if(nums[i]!=0){
                nums[n++]=nums[i];          
            }        
        }
        
        for(n;n<l;n++)
            nums[n]=0;
    }
};
```
* # 总结体会
  将数组内不为0的数字依次前移，并同时标记数组中0的个数，最后在补零。
