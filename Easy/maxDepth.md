* # 问题分析
Given a binary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.
给定一个二叉树，找出其最大深度。

二叉树的深度为根节点到最远叶子节点的最长路径上的节点数。
* # 编程实现
```c
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if (root == NULL)
            return 0;
        
        int m = maxDepth(root->left) + 1;
        int n = maxDepth(root->right) + 1;

        if(m>n)
            return m;
        else 
            return n;
    }
};
```
* # 总结体会
用递归的方法，左右子数中，深度最大的字数就是树的最大深度。