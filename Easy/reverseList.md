* # 问题分析
Reverse a singly linked list. 
反转一个单链表。
* # 编程实现
```c
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* p = head;
        ListNode* q = NULL;
        ListNode* tmp;
        while(p){
            tmp = p->next;
            p->next = q;
            q = p;
            p = tmp;
        }
        
        return q;
    } 
};
```
```python
class Solution:
    def reverseList(self, head):

        p, q = head, None
        while p :

            temp = p.next 
            p.next = q
            q = p
            p = temp
          
        return q
```
* # 总结体会
使用三个指针遍历单链表，逐个链接点进行反转。
