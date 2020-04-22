## question


给出两个 非空 的链表用来表示两个非负的整数。其中，它们各自的位数是按照 逆序 的方式存储的，并且它们的每个节点只能存储 一位 数字。

如果，我们将这两个数相加起来，则会返回一个新的链表来表示它们的和。

您可以假设除了数字 0 之外，这两个数都不会以 0 开头
## code

```python

class Solution:
    def addTwoNumbers(self, l1, l2):
        head = ListNode(0)
        pre = head
        c = 0
        while l1 or l2 or c:
            sum_list = 0
            if l1:
                sum_list+= l1.val
                l1 = l1.next
            if l2:
                sum_list+= l2.val
                l2 = l2.next
            sum_list+=c
            c = sum_list // 10
            pre.next = ListNode(sum_list % 10)
            pre = pre.next
        
        return head.next
```
## analysis
