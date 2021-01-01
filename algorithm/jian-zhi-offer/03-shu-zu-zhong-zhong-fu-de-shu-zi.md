---
description: 2020.01.01
---

# 03 数组中重复的数字

![https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/](../../.gitbook/assets/image%20%281%29.png)

**Noob's Solution :**

```text
class Solution {
    public int findRepeatNumber(int[] nums) {
        int size = nums.length;
        int[] box = new int[size];
        for(int i = 0;i < size;i++)
        {
            if(box[nums[i]] == 0)
                box[nums[i]] = 1;
            else
                return nums[i];
        }
        return -1;
    }
}
```

**God's Solution \(CS\_Note\): 时间O\(n\) 空间O\(1\)**

```text
public boolean duplicate(int[] nums, int length, int[] duplication) {
    if (nums == null || length <= 0)
        return false;
    for (int i = 0; i < length; i++) {
        while (nums[i] != i) {
            if (nums[i] == nums[nums[i]]) {
                duplication[0] = nums[i];
                return true;
            }
            swap(nums, i, nums[i]);
        }
    }
    return false;
}

private void swap(int[] nums, int i, int j) {
    int t = nums[i];
    nums[i] = nums[j];
    nums[j] = t;
}

```

三种方法,排序

```java
Arrays.sort(nums);
```

,哈希表

```java
Map<Integer, Integer> map = new HashMap<>();
```

和 数字交换. 

该用数据结构的时候就尽管调用.

