
## question
给定一个含有 n 个正整数的数组和一个正整数 s ，找出该数组中满足其和 ≥ s 的长度最小的连续子数组。如果不存在符合条件的连续子数组，返回 0。
## code
```python
class Solution:
    def minSubArrayLen(self, s: int, nums: List[int]) -> int:
        if nums == []:
            return 0
        i, j = 0, 0
        l = len(nums)
        l_min = l +1
        re = 0
        while  i < l:
            if re < s and j <l:
                re += nums[j]
                j+=1
            else:
                re -= nums[i]
                i+=1
            if re >= s:
                l_tmp = j - i
                l_min = min(l_tmp, l_min)
        if l_min == l +1:
            return 0
        else:
            return l_min
```
## analysis

