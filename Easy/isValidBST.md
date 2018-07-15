* # 问题分析

给定一个二叉树，判断其是否是一个有效的二叉搜索树。

Given a binary tree, determine if it is a valid binary search tree (BST).
* # 编程实现

```c
class Solution {
public:
    bool isValidBST(TreeNode* root) {
    if(!root) return true;
    vector<int> vec;
    order(root,vec);
    for(int i=0;i<vec.size()-1;i++)
   {
     if(vec[i]>=vec[i+1])
      return false;
   }
   return true;
}
 
  void order(TreeNode* root,vector<int> & vec){
    if(!root) return;
    if(root->left) 
    order(root->left,vec);
    vec.push_back(root->val);
    if(root->right) 
    order(root->right,vec);
    }
};
```

* # 总结体会

 因为二叉搜索树的中序遍历是有序的，所以要验证二叉树是否为二叉搜索树，
用中序遍历这个二叉树，若前一个结点的值大于当前结点的值，则证明这个不是二叉搜索树。
