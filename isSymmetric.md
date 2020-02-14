题目描述
```
给定一个二叉树，检查它是否是镜像对称的。

例如，二叉树 [1,2,2,3,4,4,3] 是对称的。

    1
   / \
  2   2
 / \ / \
3  4 4  3
```
Code
```
class Solution:
    def isSymmetric(self, root: TreeNode) -> bool:
        if not root: return True
        def match(l, r):
            if not l and not r: return True
            if not l or not r: return False
            return l.val == r.val and \
                match(l.left, r.right) and \
                match(l.right, r.left)
        return match(root.left , root.right)

```
