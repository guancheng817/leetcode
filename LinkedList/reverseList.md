## question
反转一个单链表。
## code
```pyhton
迭代法
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
    
        preNode = None
        currNode = head
        while currNode:
            nextNode = currNode.next
            currNode.next = preNode
            preNode = currNode
            currNode = nextNode
        return preNode
```
```python
递归法
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
    
        if not head or not head.next:
            return head
        
        Node = head.next
        nextNode = self.reverseList(Node)
        Node.next = head
        head.next = None
        
        return nextNode
```
## analysis