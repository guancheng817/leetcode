## question
根据每日 气温 列表，请重新生成一个列表，对应位置的输入是你需要再等待多久温度才会升高超过该日的天数。如果之后都不会升高，请在该位置用 0 来代替。

例如，给定一个列表 temperatures = [73, 74, 75, 71, 69, 72, 76, 73]，你的输出应该是 [1, 1, 4, 2, 1, 1, 0, 0]。

提示：气温 列表长度的范围是 [1, 30000]。每个气温的值的均为华氏度，都是在 [30, 100] 范围内的整数。


## code
```python
class Solution:
    def dailyTemperatures(self, T):
        stack = []
        t_length = len(T)
        res_list = [0 for _ in range(t_length)]

        for key,value in enumerate(T):
            if stack:
                while stack and T[stack[-1]] < value:
                    res_list[stack[-1]] = key - stack[-1]
                    stack.pop()

            stack.append(key)

        return res_list
```
## analysis
利用单调栈，栈中元素,按递增顺序或者递减顺序排列。
单调栈的最大好处就是时间复杂度是线性的,每个元素遍历一次!

单调递增栈可以找到左起第一个比当前数字小的元素
单调递减栈可以找到左起第一个比当前数字大的元素
