* # 问题分析
给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串，判断字符串是否有效。

有效字符串需满足：

左括号必须用相同类型的右括号闭合。
左括号必须以正确的顺序闭合。
注意空字符串可被认为是有效字符串。
* # 编程实现
```c
class Solution {
public:
    bool isValid(string s) {
      stack<char> stk;  
        int i,l=s.size();  
        if(l==0) 
        return true;  
      for(i=0;i<l;i++)  
            {  
                if(stk.empty())  
                    stk.push(s[i]);  
                else if(stk.top()=='('&&s[i]==')'||  
                      stk.top()=='['&&s[i]==']'||  
                      stk.top()=='{'&&s[i]=='}')   
                        stk.pop();  
                else  
                    stk.push(s[i]);  
                  
            }  
            return stk.empty(); 
    }
};
```
* # 总结体会
 若栈为空，则当前元素入栈，当栈顶元素与当前元素无法匹配时，也入栈，若匹配，则栈顶元素出栈，最后判断栈是否为空即可。