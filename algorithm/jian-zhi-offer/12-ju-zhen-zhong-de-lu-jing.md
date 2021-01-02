---
description: 2020.01.02
---

# 12 矩阵中的路径

![https://leetcode-cn.com/problems/ju-zhen-zhong-de-lu-jing-lcof/](../../.gitbook/assets/image%20%286%29.png)

Noob's Solution\(辣鸡代码 \[执行用时：95 ms, 在所有 Java 提交中击败了5.02% 的用户\] \):

```text
class Solution {
    public boolean exist(char[][] board, String word) {
        boolean out = false;
        int high = board.length;
        if(high == 0)
            return false;
        int length = board[0].length;
        if(length ==0)
            return false;
        int match = 0;
        for(int x = 0;x < length;x++)
        {
            for(int y = 0; y < high;y++)
            {
                if(board[y][x] == word.charAt(0))
                {

                    out = match(board,x,y,1,word);
                    if(out == true)
                        break;
                }
            }
            if(out == true)
                break;
        }
        return out;
    }

    private boolean match(char[][] board, int x, int y, int index, String word)
    {
        char[][] board2 = new char[board.length][];
        for(int i =0; i<board.length;i++)
            board2[i] = board[i].clone();
        board2[y][x] = ' ';
        boolean next = false;
        if(index == word.length())
            return true;
        char c = word.charAt(index);
        if(y - 1 >= 0 && board2[y-1][x] == c)
        {
            next = match(board2,x,y-1,index+1,word);
            if(next == true)
                return next;
        }
        if(y +1 < board2.length && board2[y+1][x] == c)
        {
            next = match(board2,x,y+1,index+1,word);
            if(next == true)
                return next;
        }
        if(x - 1 >= 0 && board2[y][x-1] == c)
        {
            next = match(board2,x-1,y,index+1,word);
            if(next == true)
                return next;
        }
        if(x + 1 < board2[y].length && board2[y][x+1] == c)
        {
            next = match(board2,x+1,y,index+1,word);
            if(next == true)
                return next;
        }
        else
            return false;
        if(index == word.length())
            return true;
        return next;
    }
}
```

经过长时间的逻辑推导.发现Noob的代码确实是 DFS和剪纸的思想.

但是因为细节的处理不同,导致了时间相差巨大.\(比如每次循环都花费时间构造二维数组的深克隆\)

JAVA语言中的细节处理也不够简洁.

Noob代码中不同的if, 答案中 用 \|\| 轻易的就解决了 \(ORZ

别人的Solution:

```text
class Solution {
    public boolean exist(char[][] board, String word) {
        char[] words = word.toCharArray();
        for(int i = 0; i < board.length; i++) {
            for(int j = 0; j < board[0].length; j++) {
                if(dfs(board, words, i, j, 0)) return true;
            }
        }
        return false;
    }
    boolean dfs(char[][] board, char[] word, int i, int j, int k) {
        if(i >= board.length || i < 0 || j >= board[0].length || j < 0 || board[i][j] != word[k]) return false;
        if(k == word.length - 1) return true;
        board[i][j] = '\0';
        boolean res = dfs(board, word, i + 1, j, k + 1) || dfs(board, word, i - 1, j, k + 1) || 
                      dfs(board, word, i, j + 1, k + 1) || dfs(board, word, i , j - 1, k + 1);
        board[i][j] = word[k];
        return res;
    }
}


// 作者：jyd
// 链接：https://leetcode-cn.com/problems/ju-zhen-zhong-de-lu-jing-lcof/solution/mian-shi-ti-12-ju-zhen-zhong-de-lu-jing-shen-du-yo/
```

