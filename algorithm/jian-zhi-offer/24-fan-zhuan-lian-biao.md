---
description: 2020.01.22
---

# 24 反转链表

![https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/](../../.gitbook/assets/tu-pian-%20%282%29.png)



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
    public ListNode reverseList(ListNode head) {
        if(head == null || head.next == null)
            return head;
        ListNode now = head;
        ListNode later = head.next;
        now.next = null;
        while(later != null)
        {
            ListNode ch = later.next;
            later.next = now;
            now = later;
            later = ch;
        }
        return now;
    }
}
```



