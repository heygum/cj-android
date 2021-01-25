---
description: 2020.01.25
---

# 27 二叉树的镜像

![https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/](../../.gitbook/assets/tu-pian-%20%282%29.png)



Noob's Solution:

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
    public TreeNode mirrorTree(TreeNode root)
    {
        if(root == null)
            return null;
        root.left = mirrorTree(root.left);
        root.right = mirrorTree(root.right);
        TreeNode third = null;
        third = root.left;
        root.left = root.right;
        root.right = third;
        return root;
    }
}
```

本来还开了个私有函数,发现私有函数把功能都写完了..

我发现大佬写的还是更简洁嘛...

```text
class Solution {
    public TreeNode mirrorTree(TreeNode root) {
        if(root == null) return null;
        TreeNode tmp = root.left;
        root.left = mirrorTree(root.right);
        root.right = mirrorTree(tmp);
        return root;
    }
}


作者：jyd
链接：https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/solution/mian-shi-ti-27-er-cha-shu-de-jing-xiang-di-gui-fu-/
来源：力扣（LeetCode）
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```



