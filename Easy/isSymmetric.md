* # 问题分析
Given a binary tree, check whether it is a mirror of itself 。
给定一个二叉树 ，判断是否为镜像对称。
* # 编程实现

```c
class Solution {
public:
    bool isSymmetric(TreeNode* root) {
        if(!root)
        return true;  
        return checkSymmetric(root->left,root->right);
    }
    
    bool checkSymmetric(TreeNode* left,TreeNode* right){
            if(!left && !right)
                return true;
            if(!left || !right)
                return false;
            return checkSymmetric(left->left,right->right)&&checkSymmetric(left->right,right->left)&&(left->val==right->val); 
        }
};
```
* # 总结体会
 用递归的方法，判断left->left==right->right，以及left->right==right->left。
