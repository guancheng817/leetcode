## question

给定一个链表，旋转链表，将链表每个节点向右移动 k 个位置，其中 k 是非负数。
## code
```python
class Solution:
    def rotateRight(self, head: ListNode, k: int) -> ListNode:
        if not head or not head.next:
            return head
        
        old_tail = head
        n = 1
        while old_tail.next:
            old_tail = old_tail.next
            n+=1
        old_tail.next = head
        
        new_tail = head
        
        for i in range(n - k%n -1):
            new_tail = new_tail.next
        
        new_head = new_tail.next
        new_tail.next = None
        
        return new_head
```

## analysis
- 先将链表闭合成环
- 找到相应的位置断开这个环，确定新的链表头和链表尾
