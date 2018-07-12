* # 问题分析
Given a singly linked list, determine if it is a palindrome.

请检查一个链表是否为回文链表。

* # 编程实现
```c
class Solution {
public:
    bool isPalindrome(ListNode* head) {
     ListNode *fast=head,*slow=head;
     stack<ListNode*> s;
    
     while(fast != NULL && fast->next != NULL)
     {
         s.push(slow);
         slow = slow->next;
         fast = fast->next->next;
     }
     if(fast !=NULL)
     {
         slow=slow->next;
     }
     while(slow!=NULL)
     {
         if(slow->val!=s.top()->val)
             return false;
         s.pop();
         slow = slow->next;
     }
        return true;
    }
};
```
* # 总结体会
 设置一个快指针和一个慢指针，将链表的前半部分结点存入栈中，然后与后半部分结点进行逐个比较，若相同，则为回文链表。注意结点奇偶的情况。
