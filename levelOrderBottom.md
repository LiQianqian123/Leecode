题目要求
```
给定一个二叉树，返回其节点值自底向上的层次遍历。 （即按从叶子节点所在层到根节点所在的层，逐层从左向右遍历）

例如：
给定二叉树 [3,9,20,null,null,15,7],

    3
   / \
  9  20
    /  \
   15   7
返回其自底向上的层次遍历为：

[
  [15,7],
  [9,20],
  [3]
]
```
Code
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def levelOrderBottom(self, root: TreeNode) -> List[List[int]]:
        result = []
        current = [root]
        
        while current:
            cur_layer_val = [] #当前层存储的值
            next_layer_node = [] # 下一层的节点，无论存不存在都可以存
            for node in current:
                if node:
                    cur_layer_val.append(node.val)
                    next_layer_node.extend([node.left,node.right])
            if cur_layer_val:
                result.append(cur_layer_val)
            current = next_layer_node
        result.reverse()
        return result
```
