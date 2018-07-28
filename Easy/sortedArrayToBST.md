* # 问题分析
Given an array where elements are sorted in ascending order, convert it to a height balanced BST.

For this problem, a height-balanced binary tree is defined as a binary tree in which the depth of the two subtrees of every node never differ by more than 1.
将一个按照升序排列的有序数组，转换为一棵高度平衡二叉搜索树。

本题中，一个高度平衡二叉树是指一个二叉树每个节点 的左右两个子树的高度差的绝对值不超过 1。

示例:
* # 编程实现
```c
class Solution {
public:  
    TreeNode* sortedArrayToBST(vector<int>& nums) {
        return  bst(nums, 0 , nums.size()-1 );
    }
    
    TreeNode* bst(vector<int>& nums , int left, int right){
        if(left > right) return NULL;
        int mid = (left+right)/2; 
        TreeNode *root = new TreeNode(nums[mid]); //根结点，为当前数组中间值
        root->left = bst(nums, left, mid-1); //根结点的左孩子为左半段数组的中间值
        root->right = bst(nums, mid+1, right); //根结点的右孩子为右半段数组的中间值
        
         return root;
    }  
};  
class Solution:    
    def bst(self,left,right,nums):
        if left > right:    
            return None
        mid = left + (right-left)//2
        root = TreeNode(nums[mid])

        root.left = self.bst(left,mid-1,nums)
        root.right = self.bst(mid+1,right,nums)

        return root   
    def sortedArrayToBST(self, nums):
        """
        :type nums: List[int]
        :rtype: TreeNode
        """
        return self.bst(0,len(nums)-1,nums)
```
* # 总结体会
由题中可知平衡搜索树的特点，发现平衡二叉搜索树的根节点的值恰好时所有节点值得中间值，若节点个树数为偶数个，则是靠前那个。用二分查找的方式，先将中间节点作为根节点，根节点的左子树为左半段数组的中间值，右子树为右半段节点的中间值。
