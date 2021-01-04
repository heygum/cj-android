---
description: 2020.01.03
---

# 14-I 剪绳子

![https://leetcode-cn.com/problems/jian-sheng-zi-lcof/](../../.gitbook/assets/image%20%289%29.png)

别人的Solution:

```text
class Solution {
    public int cuttingRope(int n) {
        if(n <= 3) return n - 1;
        int a = n / 3, b = n % 3;
        if(b == 0) return (int)Math.pow(3, a);
        if(b == 1) return (int)Math.pow(3, a - 1) * 4;
        return (int)Math.pow(3, a) * 2;
    }
}

// jyd
// https://leetcode-cn.com/problems/jian-sheng-zi-lcof/solution/mian-shi-ti-14-i-jian-sheng-zi-tan-xin-si-xiang-by/

```



