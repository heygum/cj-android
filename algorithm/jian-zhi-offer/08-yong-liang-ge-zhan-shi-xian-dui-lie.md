---
description: 2021.01.02
---

# 09 用两个栈实现队列

![https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/](../../.gitbook/assets/image%20%286%29.png)

Noob's Solution \(互相倒\):

```text
import java.util.Stack;

class CQueue {
    Stack<Integer> stackUp;
    Stack<Integer> stackDown;

    public CQueue() {
         stackUp = new Stack<>();
         stackDown = new Stack<>();
    }

    public void appendTail(int value) {
        while(!stackUp.isEmpty())
            stackDown.push(stackUp.pop());
        stackDown.push(value);
    }

    public int deleteHead() {
        if(stackUp.isEmpty() && stackDown.isEmpty())
            return -1;
        while(!stackDown.isEmpty())
            stackUp.push(stackDown.pop());
        return stackUp.pop();
    }
}
```

别人的 Solution:

```text
class CQueue {
    Deque<Integer> stack1;
    Deque<Integer> stack2;
    
    public CQueue() {
        stack1 = new LinkedList<Integer>();
        stack2 = new LinkedList<Integer>();
    }
    
    public void appendTail(int value) {
        stack1.push(value);
    }
    
    public int deleteHead() {
        // 如果第二个栈为空
        if (stack2.isEmpty()) {
            while (!stack1.isEmpty()) {
                stack2.push(stack1.pop());
            }
        } 
        if (stack2.isEmpty()) {
            return -1;
        } else {
            int deleteItem = stack2.pop();
            return deleteItem;
        }
    }
}

// https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/solution/mian-shi-ti-09-yong-liang-ge-zhan-shi-xian-dui-l-3/

```

我悟了. 倒上去后 不用再倒回来了呜呜.

Noob‘s Solution2:

```text
import java.util.Stack;

class CQueue {
    Stack<Integer> stackUp;
    Stack<Integer> stackDown;

    public CQueue() {
         stackUp = new Stack<>();
         stackDown = new Stack<>();
    }

    public void appendTail(int value) {
        stackDown.push(value);
    }

    public int deleteHead() {
        if(stackUp.isEmpty())
            while(!stackDown.isEmpty())
                stackUp.push(stackDown.pop());
        if(stackUp.isEmpty())
            return -1;
        return stackUp.pop();
    }
}
```

JAVA官方建议使用Deque&lt;&gt; 和 new LinkedList&lt;&gt;\(\) 来代替Stack这个古早的Vector接口 我又悟了;

