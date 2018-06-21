
* # 问题分析
Given a binary tree, return the inorder traversal of its nodes' values.
给定一个二叉树，返回它的中序 遍历。
* # 编程实现

```c
class Solution {
public:
    vector<int> vec;
    vector<int> inorderTraversal(TreeNode* root) {
        if(root != NULL)
        {
            inorderTraversal(root->left);
            vec.push_back(root->val);
            inorderTraversal(root->right);
            return vec;
        }
        return vec;
    }
};
```

* # 总结体会
 按照中序遍历的规则，用递归的方式求解。