## 问题分析
以 Unix 风格给出一个文件的绝对路径，你需要简化它。或者换句话说，将其转换为规范路径。

在 Unix 风格的文件系统中，一个点（.）表示当前目录本身；此外，两个点 （..） 表示将目录切换到上一级（指向父目录）；两者都可以是复杂相对路径的组成部分

* example
输入："/../"
输出："/"
解释：从根目录向上一级是不可行的，因为根是你可以到达的最高级。
## 代码
```c
class Solution {
public:
    string simplifyPath(string path) {
        string t,res;
        stringstream ss(path);
        vector<string> v;
        while(getline(ss,t,'/')){
            if(t == "" || t == ".") continue;
            if(t == ".." && !v.empty()) v.pop_back();
            
            else if(t != "..") v.push_back(t);
        }
        
        for (string s : v)  res += "/" + s ;
        
        return res.empty()? "/":res;
    }
};
```
## 总结
### getline()
istream& getline ( istream &is , string &str , char delim );
其中，istream &is 表示一个输入流，譬如cin；

string&str表示把从输入流读入的字符串存放在这个字符串中（可以自己随便命名，str什么的都可以）；

char delim表示遇到这个字符停止读入，在不设置的情况下系统默认该字符为'\n'，也就是回车换行符（遇到回车停止读入）。

* example
while(getline(cin,line))

在这个语句中，首先getline从标准输入设备上读入字符，然后返回给输入流cin，注意了，是cin，所以while判断语句的真实判断对象是cin，也就是判断当前是否存在有效的输入流。
### stringstream
[stringstream](http://www.cppblog.com/sandywin/archive/2007/07/13/27984.aspx) 
