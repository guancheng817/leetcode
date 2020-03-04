## question

在一个给定的数组nums中，总是存在一个最大元素 。

查找数组中的最大元素是否至少是数组中每个其他数字的两倍。

如果是，则返回最大元素的索引，否则返回-1。

## code
```python
class Solution:
    def dominantIndex(self, nums: List[int]) -> int:
        max_num = max(nums)
        index = nums.index(max_num)
        nums.remove(max_num)
        for i,num in enumerate(nums):
            if num > max_num/2:
                return -1

        return index
```
## analysis

注意时间复杂度
