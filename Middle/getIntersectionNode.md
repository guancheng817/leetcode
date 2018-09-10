* # 问题分析
Write a program to find the node at which the intersection of two singly linked lists begins.
编写一个程序，找到两个单链表相交的起始节点。
* # 编程实现
```c
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode* p1=headA;
        ListNode* p2=headB;
        int l1=0;
        int l2=0;
        while(p1)
        {
         p1 = p1->next;
         l1++;
        }
        while(p2)
        {
         p2 = p2->next;
         l2++;
        }
        p1=headA;
        p2=headB;
        if(l1<l2){
            int n = l2 -l1 ;
            while(n)
            {
                p2 = p2->next;
                n--;
            }
        }
        else if(l1>l2){
           int n = l1 -l2 ;
            while(n)
            {
                p1 = p1->next;
                n--;
            }
        }
        while(p1!=p2){
            p1=p1->next;
            p2=p2->next;
        }
        return p1;
    }
};
```
```python
class Solution(object):
    def getIntersectionNode(self, headA, headB):
        l1,l2 = 0,0
        p1,p2 = headA,headB
        while p1:
            l1+=1
            p1 = p1.next
        while p2:
            l2+=1
            p2 = p2.next
        p1,p2 = headA,headB
        if l1 > l2:
            n = l1 - l2
            while n:
                p1 = p1.next
                n -=1
        
        elif l2 > l1:
            n = l2 - l1
            while n:
                p2 = p2.next
                n -=1
        while p1 != p2:
            p1 = p1.next
            p2 = p2.next
        
        return p1
```
* # 总结体会
若一条链表的长度大于另一条，则需跳过多余的长度，然后逐个比较，找到相同的节点。
