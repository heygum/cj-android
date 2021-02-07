---
description: 2020.02.07
---

# 31 栈的压入,弹出序列

![https://leetcode-cn.com/problems/zhan-de-ya-ru-dan-chu-xu-lie-lcof/](../../.gitbook/assets/image%20%2824%29.png)



```text

class Solution {
    public boolean validateStackSequences(int[] pushed, int[] popped) {
        Stack<Integer> stack = new Stack<>();
        int start = 0;
        for(int i = 0; i < pushed.length;i++)
        {
            stack.push(pushed[i]);
            while(!stack.isEmpty() && popped[start] == stack.peek())
            {
                start++;
                stack.pop();
            }
        }
        return stack.isEmpty();
    }

}
```

