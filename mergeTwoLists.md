题目描述
```
将两个有序链表合并为一个新的有序链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。 
```
Examples
```
输入：1->2->4, 1->3->4
输出：1->1->2->3->4->4
```
Code
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def initList(self, data):
        # 判空
        if len(data) == 0:
            return
        else:
            # 创建头结点
            self.head = ListNode(data[0])
            r = self.head
            p = self.head
            # 逐个为 data 内的数据创建结点, 建立链表
            for i in data[1:]:
                node = ListNode(i)
                p.next = node
                p = p.next
            return r
            
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        result_list = []
        cur = l1
        while cur is not None:
            #将链表l1中的节点值放在列表result_list中：
            #print('l1:',cur.val)
            result_list.append(cur.val)
            #print('l1',result_list)
            cur = cur.next
        cur = l2
        while cur is not None:
            #在原来列表result_list的基础上继续添加链表l2中的节点值
            result_list.append(cur.val)
            cur = cur.next
        #对得到的列表中的元素进行了排序操作
        sorted_list = sorted(result_list)
        if len(sorted_list) == 0:
            return
        else:
            #再将列表还原成链表
            node = ListNode(sorted_list[0])
            cur1 = node 
            cur2 = node
            for i in range(1, len(sorted_list)):
                cur2.next = ListNode(sorted_list[i])
                cur2 = cur2.next
            return cur1
```
