##question


##code

```python

class Solution:
    def arrayPairSum(self, nums: List[int]) -> int:
        if not nums:
            return ""

        nums.sort()
        re = 0
        
        for i in range(0, len(nums),2):
            re+= nums[i]
            
        return re
```


## analysis


