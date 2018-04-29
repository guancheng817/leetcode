* # 问题分析
给定一个二叉树，判断其是否是一个有效的二叉搜索树。
* # 编程实现
```c
class Solution {
public:
    bool isValidBST(TreeNode* root) {
        if(root == NULL)
            return true;
        stack<TreeNode*> st;
        TreeNode *pre = NULL;

        while(root || !st.empty())
        {
            if(root)
            {
                st.push(root);
                root = root->left;
            }
            else
            {
                root = st.top();
                st.pop();
                if(pre && (root->val <= pre->val))
                    return false;
                pre = root;
                root = root->right;
            }
        }
        return true;
    }
};
```
* # 总结体会
 因为二叉搜索树的中序遍历是有序的，所以要验证二叉树是否为二叉搜索树，
用中序遍历这个二叉树，若前一个结点的值大于当前结点的值，则证明这个不是二叉搜索树。