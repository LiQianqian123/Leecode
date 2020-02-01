题目描述
```
实现 strStr() 函数。
给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。
```
Examples
```
输入: haystack = "hello", needle = "ll"
输出: 2

输入: haystack = "aaaaa", needle = "bba"
输出: -1
```
Code
```
def strStr(haystack, needle):
    if len(needle) == 0:
        return 0
    else:
        return haystack.index(needle) if needle in haystack else -1
            

 
haystack='hello'
needle='ll'
out = strStr(haystack,needle)
print(out)
```
