* # 问题分析
罗马数字转整数，罗马数字包含以下七种字符：I， V， X， L，C，D 和 M。
给定一个罗马数字，将其转换成整数。输入确保在 1 到 3999 的范围内。
* # 编程实现
```c
class Solution {
public:
    int romanToInt(string s) {
        map<char,int> m;
        m['I'] = 1;
        m['V'] = 5;
        m['X'] = 10;
        m['L'] = 50;
        m['C'] = 100;
        m['D'] = 500;
        m['M'] = 1000;
        
       int sum=0;
       for(int i = 0; i < s.size(); i++)
       {  
            if( m[s[i]] >= m[s[i+1]])  
                sum += m[s[i]];  
            else  
                sum -= m[s[i]];           
        }
             return sum;  
    }
};
```
 * # 总结体会
 建一个由char到int的映射。在for循环中进行一个判断，若左边的元素大于右边的元素，则加上当前元素，否则减去。