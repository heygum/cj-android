---
description: 2020.01.03
---

# 13 机器人的运动范围

![https://leetcode-cn.com/problems/ji-qi-ren-de-yun-dong-fan-wei-lcof/](../../.gitbook/assets/image%20%287%29.png)

Noob's Solution:

思考过程: 新题转换旧题, DFS.

```text
class Solution {
    public int movingCount(int m, int n, int k) {
        if(m == 0 || n == 0)
            return 0;
        int[][] board = new int[n][m];
        int count = 0;
        count += dfs(0,0,board,k,1);
        return count;
    }

    private int dfs(int x, int y, int[][] board, int k, int count)
    {
        int  x1 = 0,x2 =0, y1 =0, y2 = 0;
        if(x >= 10)
        {
            x1 = x / 10;
            x2 = x % 10;
        }
        else
            x1 = x;
        if(y >= 10)
        {
            y1 = y /10;
            y2 = y% 10;
        }
        else
            y1 =y;

        if(x < 0 || y < 0 || x >= board[0].length || y >= board.length || x1+x2+y1+y2 > k || board[y][x] == -1)
            return 0;
        board[y][x] = -1;
        count += dfs(x-1,y,board,k,1) + dfs(x+1,y,board,k,1) + dfs(x,y-1,board,k,1) + dfs(x,y+1,board,k,1);
        return count;
    }

    public static void main(String[] args) {
        Solution s = new Solution();
        System.out.println(s.movingCount(4,4,3));
    }
}
```



别人的Solution:

```text
class Solution {
    public int movingCount(int m, int n, int k) {
        boolean[][] visited = new boolean[m][n];
        return dfs(0, 0, m, n, k, visited);
    }

    private int dfs(int i, int j, int m, int n, int k, boolean visited[][]) {
        if (i < 0 || i >= m || j < 0 || j >= n || (i/10 + i%10 + j/10 + j%10) > k || visited[i][j]) {
            return 0;
        }
        visited[i][j] = true;
        return dfs(i + 1, j, m, n, k, visited) + dfs(i - 1, j, m, n, k, visited) + 
               dfs(i, j + 1, m, n, k, visited) + dfs(i, j - 1, m, n, k, visited) + 1;
    }
}

// https://leetcode-cn.com/problems/ji-qi-ren-de-yun-dong-fan-wei-lcof/comments/
// Bk8rUn4syP
```

留下了不学无术的眼泪. 自己写的还是太复杂了.

