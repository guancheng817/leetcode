## question
给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。

不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。

## code
```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
         i = 1
         for j in range(1,len(nums)):
             if nums[j] != nums[j-1]:
                 nums[i] = nums[j]
                 i+=1
         print(nums)
         return i
```
## analysis

