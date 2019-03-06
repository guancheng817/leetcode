### 问题分析

### 代码
```c
class Solution {
class Solution {
public:
    int findLengthOfLCIS(vector<int>& nums) {
        int max = 1,i,j;
        int Max = 0;
        int len = nums.size();
        if (len ==1 ) return 1;
        for(i = 0;i< len-1; i++){
            max = 1;
            for(j = i;j < len-1;j++){
                if(nums[j+1] > nums[j]){
                    max +=1;
                    
                }
                else
                {
                    Max = max > Max? max:Max;
                    break;
                }
            }
            Max = max > Max? max:Max;
        }
        
        return Max;
    }
};
```