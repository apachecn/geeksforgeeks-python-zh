# Python |检查降序排序列表

> 原文:[https://www . geesforgeks . org/python-检查-降序-排序-列表/](https://www.geeksforgeeks.org/python-check-for-descending-sorted-list/)

列表的排序操作是许多应用中必不可少的操作。但是它充分利用了时间复杂性，因此人们希望避免这种情况。因此，为了检查这是否是必需的，知道列表是否默认反向排序，可以检查列表是否排序。让我们讨论实现这一目标的各种方法。

**方法#1:天真的方法**
检查这个最简单的方法是对第一个元素运行一个循环，检查我们是否能在那个元素之后找到比它更大的元素，如果是，列表没有反向排序。

```
# Python3 code to demonstrate 
# Check for Descending Sorted List
# using naive method 

# initializing list
test_list = [10, 8, 4, 3, 1]

# printing original list 
print ("Original list : " + str(test_list))

# using naive method to 
# Check for Descending Sorted List
flag = 0
i = 1
while i < len(test_list):
    if(test_list[i] > test_list[i - 1]):
        flag = 1
    i += 1

# printing result
if (not flag) :
    print ("Yes, List is reverse sorted.")
else :
    print ("No, List is not reverse sorted.")
```

**Output :**

```
Original list : [10, 8, 4, 3, 1]
Yes, List is reverse sorted.

```