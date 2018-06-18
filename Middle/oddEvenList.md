* # 问题分析
Given a singly linked list, group all odd nodes together followed by the even nodes. Please note here we are talking about the node number and not the value in the nodes.

You should try to do it in place. The program should run in O(1) space complexity and O(nodes) time complexity.

给定一个单链表，把所有的奇数节点和偶数节点分别排在一起。请注意，这里的奇数节点和偶数节点指的是节点编号的奇偶性，而不是节点的值的奇偶性。

请尝试使用原地算法完成。你的算法的空间复杂度应为 O(1)，时间复杂度应为 O(nodes)，nodes 为节点总数。
* # 编程实现
```c
class Solution {
public:
    ListNode* oddEvenList(ListNode* head) {
        if (!head || !head->next) return head;
        ListNode *odd = head, *even = head->next;
        while (even && even->next) {
            ListNode *tmp = odd->next;
            odd->next = even->next;
            even->next = even->next->next;
            odd->next->next = tmp;
            even = even->next;
            odd = odd->next;
        }
        return head;
    }
};
```
odd指向奇节点，even指向偶节点，把偶节点even后的那个奇节点提到odd的后面，当前的偶节点指向下一个偶节点，然后odd和even前进一步，此时even又指向偶节点，odd指向当前奇节点的末尾，依次把全部偶节点提前。
