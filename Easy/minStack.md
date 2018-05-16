* # 问题分析
设计一个支持 push，pop，top 操作，并能在常数时间内检索到最小元素的栈。

push(x) -- 将元素 x 推入栈中。
pop() -- 删除栈顶的元素。
top() -- 获取栈顶元素。
getMin() -- 检索栈中的最小元素。
* # 编程实现
```c
class MinStack {  
public:  
    /** initialize your data structure here. */  
    MinStack() {}  
    void push(int x) {
        if (Stk.empty()) {
            Stk.push(x);
            minStk.push(x);
        }
        else {
            Stk.push(x);
            if (x <= minStk.top()) minStk.push(x);
        }
    }

    void pop() {
        if (Stk.top() == minStk.top()) {
            minStk.pop();
        }
        Stk.pop();
    }

    int top() {
        return Stk.top();
    }

    int getMin() {
        return minStk.top();
    }        
private:  
     
    stack<int>minStk;  
    stack<int>Stk; 
};  
```
* # 总结体会
 设计两个栈，一个用来保存最小值，相对来说，设计两个栈来解这题还是比较容易的。其实，也可以用开两个vector数组来求解。
