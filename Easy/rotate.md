* # 旋转数组
问题描述：将包含 n 个元素的数组向右旋转 k 步。

例如，如果  n = 7 ,  k = 3，给定数组  [1,2,3,4,5,6,7]  ，向右旋转后的结果为 [5,6,7,1,2,3,4]。

* #  代码实现
void Rotate(int* nums, int numsSize, int k) {
      k = k%numsSize;  
      Reverse(arr,0,numsSize-k-1);          
      Reverse(arr,numsSize-k,numsSize-1);          
      Reverse(arr,0,numsSize-1);  
}

void Reverse(int *arr,int first,int last){      
    for(; first < last;first++,last--){
           int temp = arr[last];
           arr[last] = arr[fist];
           arr[first] = temp;
      }
}

* #  简要说明
向右循环右移k位，先将前n-k位转置，再将后k位转置，最后将整体再转置一次，即可实现。
