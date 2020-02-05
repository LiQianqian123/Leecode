题目描述
```
「外观数列」是一个整数序列，从数字 1 开始，序列中的每一项都是对前一项的描述。前五项如下：

1.     1
2.     11
3.     21
4.     1211
5.     111221
```
Code
```
class Solution:
    def countAndSay(self, n: int) -> str:
        num = []
        num.append("")
        num.append("1")
        if n==1: return num[1]
        for i in range(2,n+1):
            p = []
            s = ""
            for x in num[i-1]:
                if p==[] or x==p[0]:
                    p.append(x)
                else:
                    s += str(len(p))
                    s += p[0]
                    p = []
                    p.append(x)
            s += str(len(p))
            s += p[0]
            num.append(s)
        
        return num[n]
```
