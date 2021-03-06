* # 问题分析
Given an array of strings, group anagrams together.

给定一个字符串数组，将字母异位词组合在一起。字母异位词指字母相同，但排列不同的字符串。
* # 编程实现
```c
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
         vector<vector<string>> vec;
         unordered_map<string, vector<string>> m;
          for (auto str : strs) {
              string t = str;
              sort(t.begin(), t.end());
             m[t].push_back(str);
        }
         for (auto m1 : m) {
             vec.push_back(m1.second);
         }
        return vec;
    }
    
};
```
```python
class Solution:
    def groupAnagrams(self, strs):
        """
        :type strs: List[str]
        :rtype: List[List[str]]
        """      
        li = {}
        for st in strs:
            st_sorted = "".join(sorted(st))
            if st_sorted in li :
                li[st_sorted].append(st)
            else:
                li[st_sorted] = [st]
               
        return list(li.values())
```
* # 总结体会
把字母异位词重新排列后，会得到相同的结果，所以建立一个映射表，将每个字符串排序，排序后的字符串作为key，然后再把key对应的value存入二维数组vec中。
用哈希表存储的思想，将排序后的字符串作为键，查询字典中是否有这个字符串，有则添加，没有则建立。
