---
description: 2020.02.09
---

# 32 - III. 从上到下打印二叉树 III

![https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-iii-lcof/](../../.gitbook/assets/tu-pian-%20%287%29.png)



Noob's Solution \(双栈\):

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
    public List<List<Integer>> levelOrder(TreeNode root) {  
        List<List<Integer>> big = new ArrayList<>();
        if(root == null)
            return big;
        Stack<TreeNode> stack = new Stack<>();
        Stack<TreeNode> stack2 = new Stack<>();
        stack.add(root);
        boolean order = true;
        while(!stack2.isEmpty() || !stack.isEmpty())
        {
            List<Integer> small = new ArrayList<>(); 
            if(order)
            {
                for(int i = stack.size();i>0;i--)
                {
                    TreeNode now = stack.pop();
                    small.add(now.val);
                    if(now.left != null)
                        stack2.add(now.left);
                    if(now.right != null)
                        stack2.add(now.right);
                }
            }
            else
            {
                for(int i = stack2.size(); i > 0; i--)
                {
                    TreeNode now = stack2.pop();
                    small.add(now.val);
                    if(now.right != null)
                        stack.add(now.right);
                    if(now.left != null)
                        stack.add(now.left);
                }
            }
            big.add(small);
            order = !order;
        }
        return big;
    }
}
```

我日了 原来Java的LinkedList是双端队列 两边都能操作.

```text
class Solution {
    public List<List<Integer>> levelOrder(TreeNode root) {
        Queue<TreeNode> queue = new LinkedList<>();
        List<List<Integer>> res = new ArrayList<>();
        if(root != null) queue.add(root);
        while(!queue.isEmpty()) {
            LinkedList<Integer> tmp = new LinkedList<>();
            for(int i = queue.size(); i > 0; i--) {
                TreeNode node = queue.poll();
                if(res.size() % 2 == 0) tmp.addLast(node.val); // 偶数层 -> 队列头部
                else tmp.addFirst(node.val); // 奇数层 -> 队列尾部
                if(node.left != null) queue.add(node.left);
                if(node.right != null) queue.add(node.right);
            }
            res.add(tmp);
        }
        return res;
    }
}

作者：jyd
链接：https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-iii-lcof/solution/mian-shi-ti-32-iii-cong-shang-dao-xia-da-yin-er--3/
来源：力扣（LeetCode）
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```

