题目描述
```
编写一个函数来查找字符串数组中的最长公共前缀。
如果不存在公共前缀，返回空字符串 ""。
```
Examples
```
输入: ["flower","flow","flight"]
输出: "fl"

输入: ["dog","racecar","car"]
输出: ""
解释: 输入不存在公共前缀。
```
Note
```
所有输入只包含小写字母 a-z 。
```
Code
```
#方法一
#利用字符串的ascll值排，只需比较ascll值最大最小的字符串的公共前缀就是整个数组的公共前缀
def longestCommonPrefix(strs):
    if not strs: return""
    smin=min(strs)
    smax=max(strs)
    for i, x in enumerate(smin):
        #字符串部分相同
        if x != smax[i]:
            return smax[:i]
    #全部相同
    return smin


#方法二
#使用zip解法，将每个字符串相同位置的字母提出来放在一起为charalist
#set()提取出字符串中不重复的元素,如果长度是1就代表都是相同的
#只要三个不是都相同就退出循环
def longestCommonPrefix(strs):
    if not strs: return""
    result = ""
    for charalist in zip(*strs):
        if len(set(charalist)) == 1 :
            result += charalist[0]
        else:
            break
    return result



strs= ["flower","flow","flight"]
out= longestCommonPrefix(strs)
print(out)
```
