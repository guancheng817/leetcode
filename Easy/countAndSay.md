* # 问题分析
报数序列是指一个整数序列，按照其中的整数的顺序进行报数，得到下一个数。其前五项如下
1.     1
2.     11
3.     21
4.     1211
5.     111221
The count-and-say sequence is the sequence of integers with the first five terms as following:
1 is read off as "one 1" or 11.
11 is read off as "two 1s" or 21.
21 is read off as "one 2, then one 1" or 1211.
* # 编程实现
```c
class Solution {
public:
    string countAndSay(int n) {
          if(n==1)
            return "1";
        string re =countAndSay(n-1);
        string s;
        int count=1;
        for(int i=0;i<re.size()-1;i++)
        {
            if(re[i+1]==re[i])
                count++;
            else
            {
                s.push_back(count+'0');
                s.push_back(re[i]);
                count=1;
            }
        }
        s.push_back(count+'0');
        s.push_back(re[re.size()-1]);
        return s;
    }
};
```
* # 总结体会
 一开始题目读不太懂，然后多看了几遍题目，才明白题目的要求。本题最好的方式就是用递归来求解，运算时间相对来说会比较快。