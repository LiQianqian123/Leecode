题目描述
```
给定一个排序链表，删除所有重复的元素，使得每个元素只出现一次。
```
Code
```
Definition for singly-linked list.
class ListNode:
   def __init__(self, x):
       self.val = x
       self.next = None
class Solution(object):
	def deleteDuplicates(self, head):
		"""
		:type head: ListNode
		:rtype: ListNode
		"""
		if not (head and head.next):
			return head
		i,j = head,head
		while j:
			# 如果i不等于j，则i前进一位，然后将j的值赋给i
			if i.val!=j.val:
				i = i.next
				i.val = j.val
			# 不管i是否等于j，j每次都前进一位
			j = j.next
		i.next = None
		return head
```
