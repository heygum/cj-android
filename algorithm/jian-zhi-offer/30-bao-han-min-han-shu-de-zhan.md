---
description: 2020.1.27
---

# 30 包含min函数的栈

![https://leetcode-cn.com/problems/bao-han-minhan-shu-de-zhan-lcof/](../../.gitbook/assets/tu-pian-%20%282%29.png)

Noob's 被提醒后的 Solution 好像没啥人这么写 特别是这个指向last的Node:

```text
class MinStack {
    private int size;
    private int min;
    private class Node {
        int val;
        Node last;
        int min;
        public Node()
        {
            val = 0;
            min = 0;
            last = null;
        }
    }
    private Node cur;
    /** initialize your data structure here. */
    public MinStack() {
        min = 0;
        size = 0;
        cur = new Node();
    }
    
    public void push(int x) {
        cur.val = x;
        if(size == 0)
            min = x;
        else
        {
            min = cur.last.min;
            min = x<=min?x:min;
        }
        cur.min = min;
        size++;
        Node next = new Node();
        next.last = cur;
        cur = next;
    }
    
    public void pop() {
        cur = cur.last;
        size--;
    }
    
    public int top() {
        return cur.last.val;
    }
    
    public int min() {
        return cur.last.min;
    }
}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(x);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.min();
 */
```

大佬写的\(我刚开始的思路\):

```text
class MinStack {
    Stack<Integer> A, B;
    public MinStack() {
        A = new Stack<>();
        B = new Stack<>();
    }
    public void push(int x) {
        A.add(x);
        if(B.empty() || B.peek() >= x)
            B.add(x);
    }
    public void pop() {
        if(A.pop().equals(B.peek()))
            B.pop();
    }
    public int top() {
        return A.peek();
    }
    public int min() {
        return B.peek();
    }
}

作者：jyd
链接：https://leetcode-cn.com/problems/bao-han-minhan-shu-de-zhan-lcof/solution/mian-shi-ti-30-bao-han-minhan-shu-de-zhan-fu-zhu-z/
来源：力扣（LeetCode）
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```

原来就算是实现栈,也可以调用所有数据结构...不用从底层实现.

