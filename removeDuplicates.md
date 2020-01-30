题目描述
```
给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。
不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。
```
Examples
```
给定数组 nums = [1,1,2], 
函数应该返回新的长度 2, 并且原数组 nums 的前两个元素被修改为 1, 2。 
你不需要考虑数组中超出新长度后面的元素。

给定 nums = [0,0,1,1,1,2,2,3,3,4],
函数应该返回新的长度 5, 并且原数组 nums 的前五个元素被修改为 0, 1, 2, 3, 4。
你不需要考虑数组中超出新长度后面的元素。
```
Code
```
def removeDuplicates(nums):
    #使用set函数去掉重复的元素,set函数输出为set类型
    #nums=[1,1,2,3,3,4]
    nonrepetnums = set(nums)
    #print(type(nonrepetnums))
    nonrepetnums = list(nonrepetnums)
    #还要对列表进行排序，当列表中出现负数时，顺序会出错
    nonrepetnums = sorted(nonrepetnums)
    #将nums中的对应元素换成nonrepetnums中的元素
    for i in range(len(nonrepetnums)):
        nums[i]=nonrepetnums[i]
    return len(nonrepetnums)

nums = [1,1,2,2,3,4]
out = removeDuplicates(nums)
print(out)
```
