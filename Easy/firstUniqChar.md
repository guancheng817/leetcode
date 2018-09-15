
# 问题描述
给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。

# 编程实现
```c
class Solution {
public:
    int firstUniqChar(string s) {
        unordered_map<int,int> hash;
        int i;
        int l=s.length();
        if(l)
        {  
              
        for(i=0;i<l;i++)  
        {  
            hash[s[i]]++;  
        }  
        for(i=0;i<l;i++)  
        {  
            if(hash[s[i]]==1)
            {            
                return i;  
            }  
        }             
        }           
          return -1;          
    }  
 };
 ```
```c
class Solution {
public:
    int firstUniqChar(string s) {
        int l = s.size();
        if(l==0)
            return -1;
        vector<int> vec(26,0);
        for(int i=0;i<l;i++)
        {
            vec[s[i]-'a']++;
        }
        for(int i=0;i<l;i++)
        {
            if(vec[s[i]-'a']==1)
                return i;
        }
        return -1;
         
    }  
 };
```
# 总结体会
 用哈希的思想，建一个hash数组,第一次遍历，用hash统计所有字符出现的次数，第二次遍历，找出第一个出现的统计次数为1的字符。

初始化数组vec,用vec数组统计每个字母出现的次数，若为1，则是所求的那个字母。
