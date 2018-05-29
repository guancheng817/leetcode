* # 问题分析
Given a binary tree, return the level order traversal of its nodes' values. (ie, from left to right, level by level).
给定一个二叉树，返回其按层次遍历的节点值。 （即逐层地，从左到右访问所有节点）。
* # 编程实现
```c
class Solution {
public:
    vector<vector<int>> levelOrder(TreeNode* root) {
        vector<vector<int>> vec;
        if(!root) return vec;
        queue<TreeNode*> q;
        q.push(root);
        while(!q.empty()){
            vector<int> tmp;
            int size = q.size();
            while(size--){
                TreeNode* t = q.front();
                tmp.push_back(t->val);
                q.pop();
                if(t->left)
                    q.push(t->left);
                if(t->right)
                    q.push(t->right);
            }
            vec.push_back(tmp);
        }
        
        return vec;
    }
};
```
* # 总结体会
   用广度优先搜索，若每个结点不为空，将其值加入数组vec，并且出列，同时它左右子结点入列，循环。