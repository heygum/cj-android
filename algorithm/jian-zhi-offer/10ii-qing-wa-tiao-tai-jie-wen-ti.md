---
description: 2020.01.02
---

# 10-II 青蛙跳台阶问题

![https://leetcode-cn.com/problems/qing-wa-tiao-tai-jie-wen-ti-lcof/](../../.gitbook/assets/image%20%285%29.png)

我用找规律的方法....发现是斐波那契 于是改了a值复制了过去 ORZ

```text
class Solution {
    public int numWays(int n) {
        int a = 1, b = 1, sum;
        for(int i = 0; i < n; i++){
            sum = (a + b) % 1000000007;
            a = b;
            b = sum;
        }
        return a;
    }
}
```



