## question

根据逆波兰表示法，求表达式的值。

有效的运算符包括 +, -, *, / 。每个运算对象可以是整数，也可以是另一个逆波兰表达式。

说明：

- 整数除法只保留整数部分。
- 给定逆波兰表达式总是有效的。换句话说，表达式总会得出有效数值且不存在除数为 0 的情况。

## code

```python
class Solution:
    def evalRPN(self, tokens) -> int:
        stack = []

        ops = ['/','*','+','-']
        for i in tokens:
            if i not in ops:
                i  = int(i)
                stack.append(i)
            else:
                top = stack.pop()
                sub_top = stack.pop()
                if i == '/':
                    stack.append(int(sub_top / top))
                elif i == '*':
                    stack.append(sub_top * top)
                elif i == '+':
                    stack.append(sub_top + top)
                elif i == '-':
                    stack.append(sub_top - top)

        return  stack[-1]

```


## annalysis
python3 b / a 会转为小数计算，所以直接 int(b / a)， 不能 b // a
