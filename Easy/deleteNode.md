
* # 问题分析
请编写一个函数，使其可以删除某个链表中给定的（非末尾的）节点，您将只被给予要求被删除的节点。

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
class Solution(object):
    def deleteNode(self, node):
        """
        :type node: ListNode
        :rtype: void Do not return anything, modify node in-place instead.
        """
        
        node.val = node.next.val
        node.next = node.next.next


```c
class Solution {
public:
    void deleteNode(ListNode* node) {
      
        node->val=node->next->val;
        node->next=node->next->next;
    }
    
};
```

```
* # 总结体会
 
将下个节点赋给要删除的节点，然后删除下一个节点即可。
