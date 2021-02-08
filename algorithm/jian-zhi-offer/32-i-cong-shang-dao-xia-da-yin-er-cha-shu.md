---
description: 2020.02.08
---

# 32 - I  从上到下打印二叉树

![https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/](../../.gitbook/assets/image%20%2825%29.png)

```text
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
 
class Solution {
    public int[] levelOrder(TreeNode root) {
        if(root == null)
            return new int[0];
        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(root);
        ArrayList<Integer> out = new ArrayList<>();
        while(!queue.isEmpty())
        {
            TreeNode pump = queue.poll();
            out.add(pump.val);
            if(pump.left != null)
                queue.add(pump.left);
            if(pump.right != null)
                queue.add(pump.right);

        }
        int[] ans = new int[out.size()];
        for(int i = 0; i < out.size();i++)
            ans[i] = out.get(i);
        return ans;
    }
}
```



