## question


## code
```python
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        if k == len(nums):
            pass
        else:
            l = len(nums)
            nums[:l-k] = nums[l-k-1::-1]
            nums[l-k:] = nums[l -1 : l-k-1:-1]
            nums.reverse()
```

## analysis
