* # 问题分析
Given a m x n matrix, if an element is 0, set its entire row and column to 0. Do it in-place.

给定一个 m x n 的矩阵，如果一个元素为 0，则将其所在行和列的所有元素都设为 0。请使用原地算法。
* # 编程实现
```c
class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        if(matrix.size() == 0) 
            return;
        bool rowZero = false, colZero = false; // 记录哪些元素的行列需要置零，判断首行首列是否要置0
        for(int i = 0; i < matrix.size(); i++){
            for(int j = 0; j < matrix[0].size(); j++){
                if(i != 0 && j != 0 && matrix[i][j] == 0){
                    matrix[i][0] = 0;
                    matrix[0][j] = 0;
                } else if (matrix[i][j] == 0){  // 若首行首列为零，将其标记。
                    rowZero = i == 0 ? true : rowZero;
                    colZero = j == 0 ? true : colZero;
                }
            }
        }
        
        for(int i = 1; i < matrix.size(); i++){    // 将除首行首列的元素置零
            for(int j = 1; j < matrix[0].size(); j++){
                if(matrix[0][j] == 0 || matrix[i][0] == 0){
                    matrix[i][j] = 0;
                }
            }
        }

        for(int i = 0; colZero && i < matrix.size(); i++){ //首列置零
            matrix[i][0] = 0;
        }
  
        for(int j = 0; rowZero && j < matrix[0].size(); j++){ //首行置零
            matrix[0][j] = 0;
        }
    }
};
```
```python
class Solution:
    def setZeroes(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: void Do not return anything, modify matrix in-place instead.
        """
        l1 = []
        
        for i in range(len(matrix)):
            for j in range(len(matrix[i])):
                if  matrix[i][j]==0:
                    l1.append((i,j))
        
        for i,j in  l1:
            matrix[i] = [0]*len(matrix[i])
            for k in range(len(matrix)):
                matrix[k][j] = 0
        
        return 
```
* # 总结体会
  使用原地算法求解，记录除首行首列的元素外，哪些元素的行列需要置0，并且用两个bool变量记录首行首列是否
有元素为0，将其他元素为0的行列置零后，再判断是否需要将首行首列置0.
