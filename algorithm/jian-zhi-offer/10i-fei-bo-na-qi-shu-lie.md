---
description: 2020.01.02
---

# 10-I 斐波那契数列

![https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/](../../.gitbook/assets/image%20%287%29.png)

```text
class Solution {
    public int fib(int n) {
        if(n == 0 || n ==1)
            return n;
        else
            return (fib(n-1)+fib(n-2))%1000000007;
    }
}  //超时
```

官方:

```text
class Solution {
    public int fib(int n) {
        int a = 0, b = 1, sum;
        for(int i = 0; i < n; i++){
            sum = (a + b) % 1000000007;
            a = b;
            b = sum;
        }
        return a;
    }
}
```

