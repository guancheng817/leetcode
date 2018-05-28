* # 问题分析
Given a binary tree, check whether it is a mirror of itself 。
给定一个二叉树 ，判断是否为镜像对称。
* # 编程实现

```c
class Solution {
public:
    bool isSymmetric(TreeNode* root) {
        
     if(root == NULL)
        return true;
         
            return symmetric(root->left,root->right);
    }
    
    bool symmetric(TreeNode* left,TreeNode* right){
            if(left == NULL && right == NULL)
                return true;
            if(left == NULL || right == NULL)
                return false;
            return (left->val==right->val)&&symmetric(left->left,right->right)&&symmetric(left->right,right->left);
        }
};
```
* # 总结体会
 用递归的方法，判断left->left==right->right，以及left->right==right->left。