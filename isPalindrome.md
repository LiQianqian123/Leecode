题目描述
```
判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。
```
Examples
```
输入: 121
输出: true

输入: -121
输出: false
解释: 从左向右读, 为 -121 。 从右向左读, 为 121- 。因此它不是一个回文数。

输入: 10
输出: false
解释: 从右向左读, 为 01 。因此它不是一个回文数。
```
Code
```
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x<0:
            return False
        else:
            str_x=str(x)
            a=str_x[len(str_x)-1::-1]
            if int(a)==x:
                return True
            else:
                return False
```
