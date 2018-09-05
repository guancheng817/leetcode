* # 问题分析
Remove all elements from a linked list of integers that have value val.
删除链表中的节点
* # 编程实现
```c
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) {
        if(head == NULL) 
            return head;
        ListNode *p = head, *q = head->next;
        while(q != NULL) {
            if(q->val == val) {
                p->next = q->next;
                q = q->next;
            }else{
                p = p->next;
                q = q->next;
            }
        }
        if(head->val == val) 
            head = head->next;
        return head;
    }
};
```
* # 总结体会
设置两个指针，一个指向头结点，一个指向头结点的下一个节点。进行逐个判断每个节点值是否等于val，然后前进指针。最后再次判断头结点是否等于val
