---
description: 2020.01.04
---

# 15 二进制中1的个数

![https://leetcode-cn.com/problems/er-jin-zhi-zhong-1de-ge-shu-lcof/](../../.gitbook/assets/image%20%288%29.png)

Noob's Solution: 这波啊 这波叫做暴力破解

```text
public class Solution {
    // you need to treat n as an unsigned value
    public int hammingWeight(int n) {
        String out = Integer.toBinaryString(n);
        System.out.println(out);
        int count = 0;
        for(int i = 0;i< out.length();i++)
        {
            if(out.charAt(i) == '1')
                count++;
        }
        return count;
    }
}
```

别人的 Solution:

```text
public class Solution {
    public int hammingWeight(int n) {
        int res = 0;
        while(n != 0) {
            res++;
            n &= n - 1;
        }
        return res;
    }
}

// https://leetcode-cn.com/problems/er-jin-zhi-zhong-1de-ge-shu-lcof/solution/mian-shi-ti-15-er-jin-zhi-zhong-1de-ge-shu-wei-yun/

```

遇到数位运算是, 就要使用按位运算, & \| 等等..熟记于心 Java的移位 是 &gt;&gt;&gt;, &lt;&lt;&lt;.

