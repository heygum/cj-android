---
description: 2020.01.02
---

# 11 旋转数组的最小数字

![https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/](../../.gitbook/assets/image%20%285%29.png)

Noob's Solution:

```text
class Solution {
    public int minArray(int[] numbers) {
        int size = numbers.length;
        if (size == 0)
            return -1;
        int min = numbers[0];
        for (int i = 0; i < size-1; i++) {
            if (numbers[i+1] < numbers[i])
                min = numbers[i+1];
        }
        return min;
    }
}
```

二分:

```text
class Solution {
    public int minArray(int[] numbers) {
        int low = 0;
        int high = numbers.length - 1;
        while (low < high) {
            int pivot = low + (high - low) / 2;
            if (numbers[pivot] < numbers[high]) {
                high = pivot;
            } else if (numbers[pivot] > numbers[high]) {
                low = pivot + 1;
            } else {
                high -= 1;
            }
        }
        return numbers[low];
    }
}

// https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/solution/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-by-leetcode-s/

```

