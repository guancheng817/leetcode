## quesiton

给定正整数 n，找到若干个完全平方数（比如 1, 4, 9, 16, ...）使得它们的和等于 n。你需要让组成和的完全平方数的个数最少。

输入: n = 12
输出: 3 
解释: 12 = 4 + 4 + 4.
## code

```python
class Solution:
    def numSquares(self, n: int) -> int:
        from queue import Queue
        q = Queue()
        q.put((n,0))
        seen = set()
        while not q.empty():
            num, depth = q.get()
            a = num
            for i in range(1, n):
                a = num - i**2
                if a < 0:
                    break
                elif a == 0:
                    return depth+1
                elif a not in seen:
                    q.put((a, depth+1))
                    seen.add(a)
        return depth+1

 def numSquares(self, n):
        """
        :type n: int
        :rtype: int
        """
        while n % 4 == 0: 
            n /= 4 
        if n % 8 == 7: 
            return 4 
        a = 0 
        while a**2 <= n: 
            b = int((n - a**2)**0.5) 
            if a**2 + b**2 == n: 
                return (not not a) + (not not b) 
            a += 1 
        return 3

```


## analysis
利用BFS求解
或者利用四平方定理:任何一个正整数都可以表示成不超过四个整数的平方之和。
$$ n = 4^{a} \cdot (8b+7) $$


