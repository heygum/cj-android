---
description: 2020.01.12
---

# 17 打印从1到最大的n位数

![https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/](../../.gitbook/assets/image%20%289%29.png)

Noob's Solution:

```text
class Solution {
    public int[] printNumbers(int n) {
        if(n <= 0)
            return null;
        int l = 1;
        while(n != 0)
        {
            l *= 10;
            n --;
        }
        int add = 1 ;
        int[] out = new int[l-1];
        while( add / l != 1)
        {
            out[add-1] = add;
            add++;
        }
        
        return out;
    }
}
```

别人 \(用了 Pow\):

```text
class Solution {
    public int[] printNumbers(int n) {
        int end = (int)Math.pow(10, n) - 1;
        int[] res = new int[end];
        for(int i = 0; i < end; i++)
            res[i] = i + 1;
        return res;
    }
}

作者：jyd
链接：https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/solution/mian-shi-ti-17-da-yin-cong-1-dao-zui-da-de-n-wei-2/
来源：力扣（LeetCode）
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```

考虑大数的看了一下,脑子说他懂了,那以后再写吧.

