题目描述
```
给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。
你可以假设数组中无重复元素。
```
Example
```
输入: [1,3,5,6], 5
输出: 2

输入: [1,3,5,6], 2
输出: 1

输入: [1,3,5,6], 7
输出: 4

输入: [1,3,5,6], 0
输出: 0
```
Code
```
def searchInsert(nums, target):
        size = len(nums)
        if size == 0:
            return 0

        # 特判
        if nums[size - 1] < target:
            return size

        left = 0
        right = size - 1

        while left < right:
            mid = (left + right) >> 1
            # 严格小于 target 的元素一定不是解
            if nums[mid] < target:
                # 下一轮搜索区间是 [mid + 1, right]
                left = mid + 1
            else:
                right = mid
        return left

nums = [1,3,5,6]
target = 3
out = searchInsert(nums,target)
print(out)
```
