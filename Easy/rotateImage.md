* # 问题分析
You are given an n x n 2D matrix representing an image.

Rotate the image by 90 degrees (clockwise).

Note:

You have to rotate the image in-place, which means you have to modify the input 2D matrix directly. DO NOT allocate another 2D matrix and do the rotation.
给定一个 n × n 的二维矩阵表示一个图像。

将图像顺时针旋转 90 度。
* # 编程实现
```c
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
         int len = matrix.size();
        for (int i = 0; i < len; i++) {
         for (int j = 0; j < len - i; j++) {
             int tmp = matrix[i][j];
             matrix[i][j] = matrix[len - j - 1][len - i - 1];
             matrix[len - j - 1][len - i - 1] = tmp;
         }
     }

    
     for (int i = 0; i < len; i++) {
         for (int j = 0; j < len / 2; j++) {
             int tmp = matrix[j][i];
             matrix[j][i] = matrix[len - j - 1][i];
             matrix[len - j - 1][i] = tmp;
         }
     }
         
    }
};
```
* # 总结体会
   首先观察数组有没有什么旋转规律，半天观察不出，查了下，可以先交换对角元素，然后再交换列元素。