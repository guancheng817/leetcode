* # 问题分析
给定两个数组，写一个方法来计算它们的交集。

例如:
给定 nums1 = [1, 2, 2, 1], nums2 = [2, 2], 返回 [2, 2]. </br>
Given two arrays, write a function to compute their intersection.

Example:
Given nums1 = [1, 2, 2, 1], nums2 = [2, 2], return [2, 2].
* # 编程实现
```c
class Solution {
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
       unordered_map<int,int> m;
       vector<int> insectArray;
       int i,j;
       for (i=0;i<nums1.size();i++)
           m[nums1[i]]++;
       for (j=0;j<nums2.size();j++) {
           if (m[nums2[j]]>0) {
               
               insectArray.push_back(nums2[j]); 
               m[nums2[j]]--;
           }
       }
       return insectArray;
    }
};
```


```c
class Solution {
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
        int i=0,j=0;
        sort(nums1.begin(),nums1.end());
        sort(nums2.begin(),nums2.end());
        vector<int> vec;
        while(i<nums1.size() && j<nums2.size()){
            if(nums1[i]==nums2[j]){
                vec.push_back(nums1[i]);
                i++;j++;
                continue;
            }
            nums1[i]>nums2[j]?j++:i++;     
        }
        return vec;
    }
};
```
```python
class Solution:
    def intersect(self, nums1, nums2):
        nums1.sort()
        nums2.sort()
        ls = []
        i,j = 0,0
        while i < len(nums1) and j <len(nums2):
            if nums1[i]==nums2[j]:
                ls.append(nums1[i])
                i+=1
                j+=1
                continue
                
            if nums1[i]>nums2[j]:
                j+=1
            else:
                i+=1
        return ls
```
* # 总结体会
  
1、开一个hash数组 m，先遍历nums1中重复的个数。
  2、第二个循环中，遍历nums2数组，将重复的元素添加到insecArray中.
将两个数组排序，用两个指针比较两个数组中的元素，若相等则放入数组中，若不等，小的那个往前移动。
