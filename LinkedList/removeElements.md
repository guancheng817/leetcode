## question


## code

```python
class Solution:
    def removeElements(self, head, val):
        """
        :type head: ListNode
        :type val: int
        :rtype: ListNode
        """
        if head == None:
            return None
        while head and head.val == val:
            head = head.next
        curNode = head
        preNode = None
        while curNode:
            if curNode.val == val:
                nextNode = curNode.next
                preNode.next = nextNode
                curNode = nextNode
                
            else:
                preNode = curNode
                curNode = curNode.next
        
        return head
```
## analysis
