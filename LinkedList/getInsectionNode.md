## question
编写一个程序，找到两个单链表相交的起始节点。
## code
```python
class Solution(object):
    def getIntersectionNode(self, headA, headB):
        p, q = headA, headB
        
        while p != q:
            if p:
                p = p.next
            else:
                p = headB
            if q:
                q = q.next
            else:
                q = headA
            
        return q
```
## analysis
        定义两个指针, 第一轮让两个到达末尾的节点指向另一个链表的头部, 最后如果相遇则为交点(在第一轮移动中恰好抹除了长度差)
        两个指针等于移动了相同的距离, 有交点就返回, 无交点就是各走了两条指针的长度,
        若无交点, 最后 null  == null ，中断whiile循环