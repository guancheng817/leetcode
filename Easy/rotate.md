* # 问题描述
旋转数组：将包含 n 个元素的数组向右旋转 k 步。

例如，如果  n = 7 ,  k = 3，给定数组  [1,2,3,4,5,6,7]  ，向右旋转后的结果为 [5,6,7,1,2,3,4]。

* #  代码实现
```c
void rotate(int* nums, int numsSize, int k) {
    k = k%numsSize;  
      Reverse(nums,0,numsSize-k-1);          
      Reverse(nums,numsSize-k,numsSize-1);          
      Reverse(nums,0,numsSize-1);  
}

void Reverse(int *nums,int start,int end){      
    for(; start < end;start++,end--){
           int s = nums[end];
           nums[end] = nums[start];
           nums[start] = s;
      }
}
```
```c
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        int n = nums.size();
        k = k%nums.size();
        reverse(nums.begin(),nums.begin()+n-k);
        reverse(nums.end()-k,nums.end());
        reverse(nums.begin(),nums.end());
    }
};
```
* #  总结体会
向右循环右移k位，先将前n-k位转置，再将后k位转置，最后将整体再转置一次，即可实现。
这次用c++ 中的revese函数求解。
