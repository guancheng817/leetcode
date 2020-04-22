## question
请判断一个链表是否为回文链表

## code

```python
class Solution:
    def isPalindrome(self, head: ListNode) -> bool:

        lst = []
        while head:
            lst.append(head.val)
            head = head.next
        
        return lst == lst[::-1]
```
## analysis
