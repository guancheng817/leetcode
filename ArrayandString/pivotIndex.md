## question


给定一个整数类型的数组 nums，请编写一个能够返回数组“中心索引”的方法。

我们是这样定义数组中心索引的：数组中心索引的左侧所有元素相加的和等于右侧所有元素相加的和。

如果数组不存在中心索引，那么我们应该返回 -1。如果数组有多个中心索引，那么我们应该返回最靠近左边的那一个。

## code

```python

class Solution:
    def pivotIndex(self, nums: List[int]) -> int:
        top_i = 0
        sum_ = sum(nums)
        if not nums:
            return -1
        for i, val in enumerate(nums):
            
            if top_i == sum_ - top_i - val:
                return i
            top_i += val

        return index

```


## analysis

注意边界情况
