## question

给定一个链表，返回链表开始入环的第一个节点。 如果链表无环，则返回 null。
## code
```python
class Solution(object):
    def detectCycle(self, head):
        hashmap = {}
        phead = head
        while phead:
            if phead in hashmap:
                return phead
            else:
                hashmap[phead] = 1
            phead = phead.next
        return None
```

```python
class Solution(object):
    def detectCycle(self, head):
        p, q = head,head
        while True:
            
            if not p or not p.next:
                return None
            p = p.next.next
            q = q.next
            if p == q:
                break
        p = head
        while p != q:
            p = p.next
            q = q.next
        return p
```
## analysis
用哈希表或者快慢指针
