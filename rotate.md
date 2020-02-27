题目描述
```
给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 
是非负数。

示例 1:
输入: [1,2,3,4,5,6,7] 和 k = 3
输出: [5,6,7,1,2,3,4]
解释:
向右旋转 1 步: [7,1,2,3,4,5,6]
向右旋转 2 步: [6,7,1,2,3,4,5]
向右旋转 3 步: [5,6,7,1,2,3,4]
```
Code
```
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        count,index,temp = 0,0,nums[0]
        done_index = [0]
        while count < len(nums):
            count,target = count+1, (index + k) % len(nums)
            temp,nums[target] = nums[target],temp
            if target not in done_index:
                index = target
            elif target + 1 < len(nums):
                index,temp = target + 1,nums[target + 1]
            done_index.append(index)
```
