## question

给定一个由整数组成的非空数组所表示的非负整数，在该数的基础上加一。

最高位数字存放在数组的首位， 数组中每个元素只存储单个数字。

你可以假设除了整数 0 之外，这个整数不会以零开头。

## code
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:
        new_l  = []
        c = 1
        digits.reverse()
        
        for i, num in enumerate(digits):
            num += c
            if num != 10 and i == 0:
                digits[i] = num
                return digits[::-1]
            elif num != 10:
                digits[i] = num 
                return digits[::-1]
            elif num == 10:
                digits[i] = 0
                
        digits[0] = 1
        digits.append(0)
                
        
        return digits
## analysis
之前返回a.reverse(),结果为空，查文档后发现a.reverse() 没有返回值.
