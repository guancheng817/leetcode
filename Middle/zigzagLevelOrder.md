* # 问题分析
Given a binary tree, return the zigzag level order traversal of its nodes' values. (ie, from left to right, then right to left for the next level and alternate between).
给定一个二叉树，返回其节点值的锯齿形层次遍历。（即先从左往右，再从右往左进行下一层遍历，以此类推，层与层之间交替进行）。
* # 编程实现
```c
class Solution {
public:

    vector<vector<int> > zigzagLevelOrder(TreeNode *root) {  
    vector<vector<int> > vec;  
        if(root == NULL)  
            return vec;  
        queue<TreeNode *> q;  
        q.push(root);  
        int flag = 0;
        while(!q.empty()){   
            TreeNode *p;  
            vector<int> sub;  
            int l = q.size(); 
            while(l--){  
                 p = q.front();  
                 q.pop();  
                 if(p->left) 
                     q.push(p->left);  
                 if(p->right) 
                     q.push(p->right);  
                 sub.push_back(p->val);  
            }  
            if(flag%2 != 0){     
                reverse(sub.begin(),sub.end());     
            }  
            vec.push_back(sub);  
            flag++; 
        }  
        return vec;  
    }  
};
```
```python
class Solution:
    def zigzagLevelOrder(self, root):
        res = []
        def bfs(root,level):
            if root != None:
                if len(res) < level + 1:
                    res.append([])
                res[level].append(root.val)
                bfs(root.left,level + 1)
                bfs(root.right,level + 1)
        bfs(root,0)
        i = 1
        while i < len(res):
            res[i].reverse()
            i += 2
        return res
```
* # 总结体会
 用bfs求解，用flag实现锯齿层次遍历，用reverse实现从右到左输出。
 python:用递归求解，最后隔层翻转。
