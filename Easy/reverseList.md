* # 问题分析
Reverse a singly linked list. 
反转一个单链表。
* # 编程实现
```c
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        
      ListNode* q = NULL;
      ListNode* temp;
      ListNode* p = head;
        while(p)
        {
            temp = p -> next;
            p -> next = q;
            q = p;
            p = temp;
        }
        return q;

    }
};
```
* # 总结体会
使用三个指针遍历单链表，逐个链接点进行反转。
