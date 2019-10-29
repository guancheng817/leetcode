##question


##code

```python

class Solution:
    def arrayPairSum(self, nums: List[int]) -> int:
        if len(nums) == 0:
            return ""
        elif len(nums) == 1:
            return min(nums[0],nums[1])
        nums.sort()
        num = 0
        i = 0
        while i<= len(nums)-2:
            num += nums[i]
            i+=2
            
        return num
```


## analysis


