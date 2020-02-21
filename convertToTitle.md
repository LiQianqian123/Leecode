题目描述
```
给定一个正整数，返回它在 Excel 表中相对应的列名称。
例如，
    1 -> A
    2 -> B
    3 -> C
    ...
    26 -> Z
    27 -> AA
    28 -> AB 
    ...
    
示例 1:
输入: 1
输出: "A"

示例 2:
输入: 28
输出: "AB"
```
Code
```
class Solution:
    def convertToTitle(self, n: int) -> str: 
        if n<=0: 
            return None 
        numA=ord("A") 
        res = ''
        while n // 26 > 0:
            res = chr((n-1)%26 + numA) + res
            n = (n-1) // 26
        if n != 0:
            res = chr(n-1+numA) + res
        return res
```
