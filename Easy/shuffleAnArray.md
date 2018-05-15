* # 问题分析
打乱一个没有重复元素的数组
// 以数字集合 1, 2 和 3 初始化数组。
int[] nums = {1,2,3};
Solution solution = new Solution(nums);

// 打乱数组 [1,2,3] 并返回结果。任何 [1,2,3]的排列返回的概率应该相同。
solution.shuffle();

// 重设数组到它的初始状态[1,2,3]。
solution.reset();

// 随机返回数组[1,2,3]打乱后的结果。
solution.shuffle();
* # 编程实现
```c
class Solution {
       vector<int> v;  
public:
    Solution(vector<int> nums): v(nums) {
        
    }
    
   
   /** Resets the array to its original configuration and return it. */
    vector<int> reset() {
         return v;  
    }
    
    /** Returns a random shuffling of the array. */
    vector<int> shuffle() {
        vector<int> data = v;
        for(int i=data.size()-1; i>=0; i--)  
            swap(data[i], data[rand()%(i+1)]);  
        return data;  
    }    
    
};
```
* # 总结体会
从数组的最后一个元素开始，选取取数组中任一元素和它交换，则选定选定该位置，依次类推，直到数组全部打乱。