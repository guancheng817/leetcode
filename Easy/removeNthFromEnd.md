* # 问题分析
给定一个链表，删除链表的倒数第 n 个节点，并且返回链表的头结点。
* # 编程实现
```c
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        ListNode *p = head;  
        ListNode *p0 = head;  
        int num = 0;  
        int tmp = 0;
        while(p != NULL)  
        {  
            num += 1;  
            p = p->next;  
        }  
        if (num == n)  
        {  
            return head->next;  
        } 
        num = num - n - 1;  
        while(num != tmp)  
        {  
            tmp += 1;  
            head = head->next;  
        }  
        head->next = head->next->next;  
        return p0;  
    }
};
```
* # 总结体会
  统计链表长度，找到被删除那个点的前驱结点，进行删除。