* # 问题分析
给定一个链表，返回链表开始入环的第一个节点。 如果链表无环，则返回 null。


* # 编程实现
```c
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        bool cycle = false;
        ListNode *start = NULL;
        if(head == NULL)
        {
            return start;
        }
        ListNode *p1,*p2;
        p1 = p2 = head;
        while(p2->next != NULL && p2->next->next != NULL)
        {
            p1 = p1->next;
            p2 = p2->next->next;
            if(p1 == p2)
            {
                cycle = true;
                p2 = head;
                while(p1 != p2)
                {
                    p1 = p1->next;
                    p2 = p2->next;                    
                }
                start = p1;
                break;
            }
                
        }      
        return cycle ? start : NULL;
    }
};
```
```python
class Solution(object):
    def detectCycle(self, head):
        cycle = False
        start = None
        if head == None:
            return start
        p1,p2 = head,head
        while p2.next != None and p2.next.next !=None :
            p1 = p1.next
            p2 = p2.next.next
            if p1 == p2:
                cycle = True
                p2 = head
                while p1!=p2 :
                    p1 = p1.next
                    p2 = p2.next
                start = p2
                break
        if cycle:
            return start
        else:
            return None
```
* # 总结体会
第一步，先判断有无环，若遇到slow == fast时，跳出循环；
第二步，调整fast=head，slow不变，此时slow与fast同步移动，若再次相遇，则为环第一个节点



