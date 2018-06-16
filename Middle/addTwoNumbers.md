* # 问题分析
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

给定两个非空链表来表示两个非负整数。位数按照逆序方式存储，它们的每个节点只存储单个数字。将两数相加返回一个新的链表。

你可以假设除了数字 0 之外，这两个数字都不会以零开头。
* # 编程实现
```c
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* head = new ListNode(0);
        ListNode* cur = head;
        int c = 0;  
       while (l1 || l2 || c)   
       {  
          int sum = (l1 ? l1->val : 0) + (l2 ? l2->val : 0) + c;  
          c = sum / 10;  
          cur->next = new ListNode(sum % 10);  
          cur = cur->next;  
          l1 = l1 ? l1->next : l1;  
          l2 = l2 ? l2->next : l2;  
       }  
      
       return head->next;  
    }
};
```
* # 总结体会
 遍历两个链表，将对应的位置的值相加，考虑进位，并为结果新建一个链表节点。