## question

给你一个整数数组 nums ，请你找出数组中乘积最大的连续子数组（该子数组中至少包含一个数字）
## code
```python
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        n = len(nums)

        max_res = -float('inf')

        cur_max = 1
        cur_min = 1

        for i in range(n):
            if nums[i] <0:
                cur_max,cur_min = cur_min,cur_max
            
            cur_max = max(cur_max*nums[i],nums[i])
            cur_min = min(cur_min*nums[i],nums[i])

            max_res = max(cur_max,max_res)

        return max_res
```
## analysis
