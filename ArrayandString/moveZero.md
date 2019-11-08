## question
给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。
输入: [0,1,0,3,12]
输出: [1,3,12,0,0]
## code
```python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        j = 0
        k = 0
        l = len(nums)
        for i in range(l):
            if nums[i] != 0:
                nums[j] = nums[i]
                j+=1  
            else:
                k +=1
            
        for i in range(k):
            nums[l-i-1] = 0
            
        return nums
```

## analysis
