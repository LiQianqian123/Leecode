题目描述
```
给定两个二进制字符串，返回他们的和（用二进制表示）。
输入为非空字符串且只包含数字 1 和 0。
```
Code
```
class Solution:
    def addBinary(self, a: str, b: str) -> str:
        a,b=int(a,2),int(b,2)
        ans=bin(a+b)
        ans=str(ans)
        ans=ans[2:]
        return ans

```
