题目描述
```
给定一个整数 n，返回 n! 结果尾数中零的数量。

示例 :
输入: 3
输出: 0
解释: 3! = 6, 尾数中没有零。
```
Code
```
class Solution:
    def trailingZeroes(self, n: int) -> int:
        if(n==0):
            return(0)

        five_num = 0
        five_num_tmp = 0
        while(n>=5):
            five_num_tmp = int(n/5)
            n = five_num_tmp
            five_num =five_num +five_num_tmp

        return(five_num)
```
