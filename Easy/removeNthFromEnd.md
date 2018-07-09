* # 问题分析
给定一个链表，删除链表的倒数第 n 个节点，并且返回链表的头结点。
* # 编程实现
```c
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        ListNode* p = head;
        ListNode* q = head;
        int sum = 0;  
        int temp = 0;
        while(p != NULL)  
        {  
            sum ++;  
            p = p->next;  
        }  
        if (sum == n)  
        {  
            return head->next;  
        } 
        sum = sum - n - 1;  
        while(temp < sum)  
        {  
            temp ++;  
            head = head->next;  
        }  
        head->next = head->next->next;  
        return q; 
    }
};
```
* # 总结体会
  统计链表长度，找到被删除那个点的前驱结点，进行删除,注意当链表长度和n相等的情况。
