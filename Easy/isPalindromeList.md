* # 问题分析
Given a singly linked list, determine if it is a palindrome.

请检查一个链表是否为回文链表。

* # 编程实现
```c
class Solution {
public:
    bool isPalindrome(ListNode* head) {
     ListNode *fast,*slow;
     fast = slow = head;
     stack<ListNode*> s;
    
     while(fast != NULL && fast->next != NULL)
     {
         s.push(slow);
         fast = fast->next->next;
         slow = slow->next;
     }
     if(fast !=NULL)
     {
         slow=slow->next;
     }
     while(slow)
     {
         if(slow->val!=s.top()->val)
             return false;
         slow = slow->next;
         s.pop();
     }
        return true;
    }
};
```
* # 总结体会
 将链表的前半部分逆转，与后半部分进行比较，若相同则为回文链表，否则不是。