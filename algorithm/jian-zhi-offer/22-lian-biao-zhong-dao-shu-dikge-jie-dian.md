---
description: 2020.01.22
---

# 22 链表中倒数第k个节点

![https://leetcode-cn.com/problems/lian-biao-zhong-dao-shu-di-kge-jie-dian-lcof/](../../.gitbook/assets/image%20%2821%29.png)

Noob's Solution:

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
    public ListNode getKthFromEnd(ListNode head, int k) {
        if(head == null)
            return null;
        ListNode out = head;
        ListNode now = head;
        for(int i = 1;i < k;i++)
        {
            now = now.next;
        }
        while(now.next != null)
        {
            out = out.next;
            now = now.next;
        }
        return out;
    }
}
```



