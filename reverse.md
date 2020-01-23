题目描述
```
给出一个 32 位的有符号整数，你需要将这个整数中每位上的数字进行反转。
```
Examples
```
1:输入: 123
  输出: 321
2:输入: -123
  输出: -321
3.输入: 120
  输出: 21
```
Note
```
-2^31<int<2^31-1
```
Code
```
class Solution:
    def reverse(self, x: int) -> int:
        if x==0:
            return 0
        else:
            str_x = str(x)
            x = ''
            if str_x[0] == '-':
                x += '-'
            x += str_x[len(str_x)-1::-1].lstrip("0").rstrip("-")
            x = int(x)
            if -2**31<x<2**31-1:
                return x
            else:
                return 0
```
