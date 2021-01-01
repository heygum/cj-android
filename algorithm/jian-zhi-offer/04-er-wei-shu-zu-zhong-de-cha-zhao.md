---
description: 2020.01.01
---

# 04 二维数组中的查找

![https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/](../../.gitbook/assets/image%20%282%29.png)

**Noob不想暴力求解然后做错了没有Solution.**

**别人的Solution\(CS\_Note\):**

```text
public boolean Find(int target, int[][] matrix) {
    if (matrix == null || matrix.length == 0 || matrix[0].length == 0)
        return false;
    int rows = matrix.length, cols = matrix[0].length;
    int r = 0, c = cols - 1; // 从右上角开始
    while (r <= rows - 1 && c >= 0) {
        if (target == matrix[r][c])
            return true;
        else if (target > matrix[r][c])
            r++;
        else
            c--;
    }
    return false;
}
```



