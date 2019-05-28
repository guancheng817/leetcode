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
```python
## 递归实现
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        if head == None or head.next == None:
            return head;
        
        new_list = self.reverseList(head.next)
        t1 = head.next
        t1.next = head
        head.next = None
        
        return new_list
```
* # 总结体会
使用三个指针遍历单链表，逐个链接点进行反转。
