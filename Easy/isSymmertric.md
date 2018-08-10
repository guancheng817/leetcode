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
```python
class Solution:  
    def symmertric(self,left,right):
        if left == None and right==None:
            return True
        if left == None or right==None:
            return False

        return (left.val == right.val) and self.symmertric(left.left,right.right) and self.symmertric(left.right,right.left)

    
    def isSymmetric(self, root):
        """
        :type root: TreeNode
        :rtype: bool
        """
        if root == None :
            return True
        return self.symmertric(root.left,root.right)
```
* # 总结体会
 用递归的方法，判断left->left==right->right，以及left->right==right->left。
