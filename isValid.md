题目描述
```
给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串，判断字符串是否有效。

有效字符串需满足：

左括号必须用相同类型的右括号闭合。
左括号必须以正确的顺序闭合。
注意空字符串可被认为是有效字符串。
```
Examples
```
输入: "()"
输出: true

输入: "()[]{}"
输出: true

输入: "(]"
输出: false
```
Code
```
#合法的情况只包括单独出现，独立并排出现和嵌套完整的不同的括号三种情况
#replace的作用是每次替换最里面的括号，要定义好循环次数
import math 
def isValid(strs):
    while '{}' in strs or '()' in strs or '[]' in strs:
        a=0
        b=2
        for i in strs:
            a += 1
        j = math.ceil(a/b)
        print(j)
        for i in range(j):    #整数不能用于遍历，可加上range()
            strs = strs.replace('()','')
            print(strs)
            strs = strs.replace('[]','')
            print(strs)
            strs = strs.replace('{}','')
            print(strs)
        if strs == '':
            return True
        else:
            return False



strs= "([{{}}])"
out= isValid(strs)
print(out)
```
