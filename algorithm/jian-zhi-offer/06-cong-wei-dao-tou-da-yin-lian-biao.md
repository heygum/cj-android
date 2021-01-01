---
description: 2020.01.01
---

# 06 从尾到头打印链表

![https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/](../../.gitbook/assets/image%20%284%29.png)



Noob's Solution:

```text
import java.util.ArrayList;

/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public int[] reversePrint(ListNode head) {
        ArrayList<Integer> out = new ArrayList<>();
        int[] realOut = {};
        if(head == null)
            return realOut;
        ListNode cur = head;
        int size= 0;
        while(cur != null)
        {
            out.add(cur.val);
            cur = cur.next;
            size++;
        }
        realOut = new int[size];
        for(int i=0;i<size;i++)
        {
            realOut[i] = out.get(size-1-i);
        }
        return realOut;
    }
}

```

\*\*\*\*[**别人的 Solution \(栈\)**:](https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/solution/mian-shi-ti-06-cong-wei-dao-tou-da-yin-lian-biao-b/)

```text
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public int[] reversePrint(ListNode head) {
        Stack<ListNode> stack = new Stack<ListNode>();
        ListNode temp = head;
        while (temp != null) {
            stack.push(temp);
            temp = temp.next;
        }
        int size = stack.size();
        int[] print = new int[size];
        for (int i = 0; i < size; i++) {
            print[i] = stack.pop().val;
        }
        return print;
    }
}

//https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/solution/mian-shi-ti-06-cong-wei-dao-tou-da-yin-lian-biao-b/

```

先进后出先说栈还是牛逼的.

我寻思我的彩笔Solution是人工模拟了栈嘛.

