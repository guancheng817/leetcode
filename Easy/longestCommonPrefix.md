* # 问题分析
编写一个函数来查找字符串数组中的最长公共前缀。
* # 编程实现
```c
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
    if(strs.size()==0) return "";

        string prifex = strs[0];      //将第一个默认为最长公共字串

        for(int i=1;i<strs.size();i++){
            // 将当前最长共同字符串和当前数组中的对比,把小的那个作为长度
            int len = prifex.size()>strs[i].size() ? strs[i].size():prifex.size();

            int j=0;
            for(j=0;j<len;j++){
                
                if(prifex[j]!=strs[i][j])
                    break;
            }      // 每个字符都比较,不满足条件就break
            
            prifex = prifex.substr(0,j);
        }

        return prifex;
    }
};
```
* # 总结体会
  上次的测试有部分测试点未测试通过，此次进行更改。将第一个字串默认为最长公共字串，依次与后面的字串的每个字符进行比较。