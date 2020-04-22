## question


## code

```python
class Solution:
    def permuteUnique(self, nums: List[int]) -> List[List[int]]:
        nums.sort()
        n = len(nums)
        visited = [False]*n
        res= []

        def backtrace(temp_list,length):
            if length == n:
                res.append(temp_list)
            for i in range(n):
                if not visited[i]:
                    if (i > 0 and nums[i] == nums[i - 1] and not visited[i - 1]):
                        continue
                    visited[i] = True
                    backtrace(temp_list + [nums[i]], length + 1)
                    visited[i] = False

        backtrace([],0)

        return res

```
## analysis


