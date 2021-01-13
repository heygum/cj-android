---
description: '2020-01-04'
---

# 14-II 剪绳子 II

![https://leetcode-cn.com/problems/jian-sheng-zi-ii-lcof/](../../.gitbook/assets/image%20%2810%29.png)

```text
class Solution {
    public int cuttingRope(int n) {
        if(n == 2)
            return 1;
        if(n ==3)
            return 2;
        int mod = 1000000007;
        long out =1;
        while(n > 4)
        {
            out *= 3;
            out %= mod;
            n -= 3;
        }
        return (int)(out*n%mod);
    }
}
```

