---
description: 2020.01.25
---

# 29 瞬时间打印矩阵

![https://leetcode-cn.com/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/](../../.gitbook/assets/tu-pian-%20%285%29.png)

```text
class Solution {
    public int[] spiralOrder(int[][] matrix) {
        if(matrix == null || matrix.length == 0)
            return new int[0];
        int s = 0;
        int z = 0;
        int x = matrix.length -1;
        int y = matrix[0].length -1;
        int size = (x+1) * (y+1);
        int[] out = new int[size];
        int num = 0;
        while(true)
        {
            for(int i = z; i <= y;i++)
                out[num++] = matrix[s][i];
            if(++s > x) break;
            for(int i = s;i <= x;i++)
                out[num++] = matrix[i][y];
            if(--y < z) break;
            for(int i = y; i >= z;i--)
                out[num++] = matrix[x][i];
            if(--x < s) break;
            for(int i = x;i >= s;i--)
                out[num++] = matrix[i][z];
            if(++z > y) break;
        }
        return out;
    }
}
```

