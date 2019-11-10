## question


## code
```python

class Solution:
    def numIslands(self, grid: List[List[str]]) -> int:
        from queue import Queue
        # dires = [[0,-1],[0,1],[-1,0],[1,0]] ## up down left right
        # m = len(grid)
        # if not m:
        #     return 0
        # n = len(grid[0])
        # if not n:
        #     return 0
        # count = 0
        # q = Queue()
        # for i in range(m):
        #     for j in range(n):
        #         if grid[i][j] == '1':
        #             q.put((i,j))
        #             count+=1
        #             while not q.empty():
        #                 cur_x, cur_y = q.get()
        #                 for dire in dires:
        #                     new_x = cur_x + dire[0]
        #                     new_y = cur_y + dire[1]
        #                     if 0 <= new_x< m and 0<=new_y< n and grid[new_x][new_y] == '1':
        #                         q.put((new_x, new_y))
        #                         grid[new_x][new_y] = '0'
        self.m = len(grid)
        if not self.m:
            return 0
        self.n = len(grid[0])
        if not self.n:
            return 0
        count = 0
        for i in range(self.m):
            for j in range(self.n):
                if grid[i][j] == '1':
                    self.dfs(grid,i,j)
                    count +=1
        return count

    def dfs(self, grid,x, y):
        if 0<=x < self.m and 0<=y <self.n and grid[x][y] == '1':
            grid[x][y] = '0'
            self.dfs(grid, x,y-1)
            self.dfs(grid, x,y+1)
            self.dfs(grid, x-1,y)
            self.dfs(grid, x+1,y)
        else:
            return    
```

## analysis
两种方式，深度优先搜搜和广度优先搜索。
