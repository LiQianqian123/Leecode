题目描述
```
给定一个二叉树和一个目标和，判断该树中是否存在根节点到叶子节点的路径，这条路径上所有节点值相加等于目标和。
说明: 叶子节点是指没有子节点的节点。

示例: 
给定如下二叉树，以及目标和 sum = 22，

              5
             / \
            4   8
           /   / \
          11  13  4
         /  \      \
        7    2      1
返回 true, 因为存在目标和为 22 的根节点到叶子节点的路径 5->4->11->2。
```
Code
```
class Solution:
	def hasPathSum(self,root,sum):
		def helper(root,c_sum): #root为DFS到的当前节点 c_sum为当前节点对应路径的数据和
			if not root: #避免了给定的root就是None的情况 也省得下面的俩helper()调用前分别需要的if root.left:和if root.right
				return
			s=c_sum+root.val #供后面使用
			if not root.left and not root.right: #表示当前节点是给定树的叶子节点
				assert s!=sum #如果s==sum就会raise AssertionError了
			else:
				helper(root.left,s) #普通的DFS 对左右子节点分别进行
				helper(root.right,s)
		try:
			helper(root,0) #初始情况下的c_sum是0
			return False #没有捕获到异常那就是没有满足要求的路径 即False
		except AssertionError: #注意assert对应的是AssertionError
			return True
```
