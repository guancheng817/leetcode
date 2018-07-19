* # 问题分析
你是产品经理，目前正在带领一个团队开发新的产品。不幸的是，你的产品的最新版本没有通过质量检测。由于每个版本都是基于之前的版本开发的，所以错误的版本之后的所有版本都是错的。

假设你有 n 个版本 [1, 2, ..., n]，你想找出导致之后所有版本出错的第一个错误的版本。

你可以通过调用 bool isBadVersion(version) 接口来判断版本号 version 是否在单元测试中出错。实现一个函数来查找第一个错误的版本。你应该尽量减少对调用 API 的次数。
You are a product manager and currently leading a team to develop a new product. Unfortunately, the latest version of your product fails the quality check. Since each version is developed based on the previous version, all the versions after a bad version are also bad.

Suppose you have n versions [1, 2, ..., n] and you want to find out the first bad one, which causes all the following ones to be bad.

You are given an API bool isBadVersion(version) which will return whether version is bad. Implement a function to find the first bad version. You should minimize the number of calls to the API.
* # 编程实现
```c 
bool isBadVersion(int version);

class Solution {
public:
    int firstBadVersion(int n) {
        int left = 1;
        int right = n;
        int flag;
        while(left<=right){
            int mid = left+(right-left)/2;
            if(isBadVersion(mid)){
                right = mid - 1;
                flag = mid;
            }
            else{
                left = mid +1;
            }
        }
        
        return flag;
   
    }
};
```
* # 总结体会
 若直接运用for循环进行线性搜索，运算将会超时，运用二分查找，可以在规定时间内解出, 当mid = （left+right)/2 时将会溢出。
