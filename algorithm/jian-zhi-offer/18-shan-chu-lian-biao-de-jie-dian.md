---
description: 2020.01.15
---

# 18 删除链表的节点

![https://leetcode-cn.com/problems/shan-chu-lian-biao-de-jie-dian-lcof/](../../.gitbook/assets/image%20%2810%29.png)



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
    public ListNode deleteNode(ListNode head, int val) {
        ListNode cur = head;
        if(head == null)
            return null;
        if(cur.val == val){
            head = cur.next;
            cur = null;
            return head;
        }
        while(cur.next != null)
        {
            if(cur.next.val == val){
                ListNode del = cur.next;
                cur.next = cur.next.next;
                del = null;
                return head;
            }
            cur = cur.next;
        }
        return head;
    }
}
```



