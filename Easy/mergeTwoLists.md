* # 问题分析
Merge two sorted linked lists and return it as a new list. 
The new list should be made by splicing together the nodes of the first two lists.<br/><br/>

将两个有序链表合并为一个新的有序链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。


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
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        
        if(l1 == NULL)
            return l2;
        else if(l2 == NULL)
            return l1;
        ListNode* qMerge = NULL;
        if(l1->val <= l2->val)
        {
            qMerge = l1;
            qMerge->next = mergeTwoLists(l1->next,l2);
        }
        else
        {
            qMerge = l2;
            qMerge->next = mergeTwoLists(l1,l2->next);
        }
        
        return qMerge;

    }
};
```
```c
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
       if(l1 == NULL && l2 == NULL) 
           return NULL;
        ListNode* list = new ListNode(1);
        ListNode* p = list;
        while( l1!=NULL && l2!=NULL)
        {
            if(l1->val <= l2->val)
            {
                p->next = l1;
                l1 = l1->next;
            }
            else
            {
                p->next = l2;
                l2 = l2->next;
            }
            p = p->next;
        }
        if(l1) 
            p->next = l1;
        else 
            p->next = l2;
        
        return list->next;
    }
};
```

* # 总结体会
 1.假如链表l1为空则返回l2，l2为空则返l1。<br/>
 2.比较两个链表第一个结点的大小，qMerge为新合并的链表的头节点。<br/>
 3.确定头节点后，在剩下的结点中，选出下一个结点去链接到第二步选出的结点后面，然后不断重复，直至链表为空。
<br/>
 这次用非递归的方式求解，效率更高。建一个的链表list，依次比较两个链表的每个节点的大小，若l1中的结点值小于l2中的结点值，则将l1链接到list中，并且l1前进，p指针也前进，直至l1或者l2为空。
