* # 问题分析
Given a linked list, determine if it has a cycle in it.<br/>
给定一个链表，判断其是否为循环链表

* # 编程实现
```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode *head) {
        ListNode* fast = head;
        ListNode* slow = head;
        while(fast && fast->next)
        {
            fast = fast->next->next;
            slow = slow->next;
            if(slow == fast)
                return true;
        }
        return false;
    }
};
class Solution(object):
    def hasCycle(self, head):
        """
        :type head: ListNode
        :rtype: bool
        """
        slow,fast = head, head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                return True
        
        return False
```
* # 总结体会
  给定两个指针，一个为快指针，一个为慢指针，快指针走的速度是慢指针的两倍，若两个指针能够再次相遇，则说明此链表是一个循环链表。
