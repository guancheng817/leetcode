## question
给定一个链表，删除链表的倒数第 n 个节点，并且返回链表的头结点。
## code
```python
class Solution:
    def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
        
        p,q = head, head
        for i in range(n):
            if p.next:
                p = p.next
            else:
                return head.next
        
        while p.next:
            p = p.next
            q = q.next
        q.next = q.next.next
        
        return head
 ```
## annalysis
快慢指针，快指针先走n步，然后快慢一起走，直到快指针走到最后，要注意的是可能是要删除第一个节点，这个时候可以直接返回head -> next