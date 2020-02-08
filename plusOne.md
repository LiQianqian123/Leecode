题目描述
```
给定一个由整数组成的非空数组所表示的非负整数，在该数的基础上加一。
最高位数字存放在数组的首位， 数组中每个元素只存储单个数字。
你可以假设除了整数 0 之外，这个整数不会以零开头。
```
Code
```
class Solution(object):
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        digits_str=''
        for i in range(len(digits)):
            digits_str+=str(digits[i])
        digits_num=int(digits_str)+1
        digits_list=list(str(digits_num))
        return digits_list
```
