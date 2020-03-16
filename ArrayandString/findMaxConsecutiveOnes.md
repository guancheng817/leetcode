## question

给定一个二进制数组， 计算其中最大连续1的个数
## code

```python
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        max_l = 0
        cnt = 0
        for i in nums:
            if i == 1:
                cnt+=1
            else:
                max_l = max(cnt, max_l)
                cnt = 0
        
        return max(cnt, max_l)


```
