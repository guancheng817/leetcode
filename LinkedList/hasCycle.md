## question


## code
```python
class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        hashmap = {}
        phead = head
        while(phead):
            if(hashmap.get(phead,0) != 0):
                return True
            else:
                hashmap[phead] = 1
            phead = phead.next
        return False
```
```python

class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        p, q = head, head
        
        while p and p.next:
            
            p = p.next.next
            q = q.next
            
            if p == q:
                return True
        return False
```
## analysis
两种办法，一种是用哈希表，一种用快慢指针
