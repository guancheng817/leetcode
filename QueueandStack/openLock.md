## question

你有一个带有四个圆形拨轮的转盘锁。每个拨轮都有10个数字： '0', '1', '2', '3', '4', '5', '6', '7', '8', '9' 。每个拨轮可以自由旋转：例如把 '9' 变为  '0'，'0' 变为 '9' 。每次旋转都只能旋转一个拨轮的一位数字。

锁的初始数字为 '0000' ，一个代表四个拨轮的数字的字符串。

列表 deadends 包含了一组死亡数字，一旦拨轮的数字和列表里的任何一个元素相同，这个锁将会被永久锁定，无法再被旋转。

字符串 target 代表可以解锁的数字，你需要给出最小的旋转次数，如果无论如何不能解锁，返回 -1。
## code

```python

class Solution:
    def openLock(self, deadends: List[str], target: str) -> int:
        from queue import Queue
        deadends = set(deadends)
        if '0000' in deadends:
            return -1

        ## dfs
        q = Queue()
        q.put(('0000', 0))

        while not q.empty():
            node, depth = q.get()
            for i in range(4):
                for add in (1,-1)
                    next_node = node[:i] + str((int(node[i])+add) % 10) + node[i+1:]
                    if next_node == target:
                        return depth+1
                    if next_node not in deadends:
                        q.put((next_node, depth+1))
                        deadends.add(next_node)

        return -1
```


## analysis
为什么这题要用 BFS(广度优先搜索) ？根据题意，我们需要找到最少的解锁步数，这实际上可以认为是在图上搜索最短路径。BFS 总是优先搜索距离根节点近的节点，因此它搜索到的路径就是最短路径

