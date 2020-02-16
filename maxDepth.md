题目描述
```
给定一个二叉树，找出其最大深度。
二叉树的深度为根节点到最远叶子节点的最长路径上的节点数。
说明: 叶子节点是指没有子节点的节点。
```
examples
```
给定二叉树 [3,9,20,null,null,15,7]，

    3
   / \
  9  20
    /  \
   15   7
返回它的最大深度 3 
```
code
```
def maxDepth(self, root):
  """
  :type root: TreeNode
  :rtype: int
  """
  # 如果节点为空，那么深度就是0
  if(not root):
    return 0
  # 否则递归的计算  max(左子树的最大深度，右子树的最大深度)
  # 不管左子树，右子树是否为空，他们的父节点肯定是不为空
  # 所以计算出的总深度要把父节点也要加上，也就是 +1
  return max( self.maxDepth(root.left), self.maxDepth(root.right) ) + 1
```
