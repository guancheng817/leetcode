## question



## code

```python

class Solution:
    def pivotIndex(self, nums: List[int]) -> int:
        import numpy
        index = -1
        top_i = 0
        sum_ = numpy.sum(nums)
        if nums == []:
            return -1
        for i in range(len(nums)):
            
            if i  == 0:
                if top_i == sum_ - nums[i]:
                    index = i
                    break
 
            elif top_i == sum_ - top_i - nums[i]:
                index = i
                break
            top_i += nums[i]
            
        return index

```


## analysis

注意边界情况
