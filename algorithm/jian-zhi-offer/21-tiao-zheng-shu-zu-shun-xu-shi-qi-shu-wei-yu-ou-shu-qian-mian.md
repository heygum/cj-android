---
description: 2020.01.19
---

# 21 调整数组顺序使奇数位于偶数前面

![https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/](../../.gitbook/assets/image%20%2821%29.png)

Noob's Solution:

```text
class Solution {
    public int[] exchange(int[] nums) {
        if(nums == null)
            return null;
        int size = nums.length;
        int pre  = 0;
        int cur = 0;
        int c = 0;
        for(int i = 0;i < size;i++) {
            if (nums[cur] % 2 == 1) {
                if (pre != cur)
                {
                    c = nums[cur];
                    nums[cur] = nums[pre];
                    nums[pre] = c;
                }
                pre++;
                cur++;
            }
            else
                cur++;
        }
        return nums;
    }
}
```

看了答案发现写的是快慢双指针. 牛牛

