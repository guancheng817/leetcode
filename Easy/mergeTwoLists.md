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

* # 总结体会
 1.假如链表l1为空则返回l2，l2为空则返l1。<br/>
 2.比较两个链表第一个结点的大小，qMerge为新合并的链表的头节点。<br/>
 3.确定头节点后，在剩下的结点中，选出下一个结点去链接到第二步选出的结点后面，然后不断重复，直至链表为空。
