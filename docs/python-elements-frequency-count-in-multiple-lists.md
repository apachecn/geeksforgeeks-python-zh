# Python–多个列表中的元素频率计数

> 原文:[https://www . geesforgeks . org/python-elements-frequency-count-in-multiple-list/](https://www.geeksforgeeks.org/python-elements-frequency-count-in-multiple-lists/)

有时在使用 Python 列表时，我们会遇到一个问题，需要提取列表中元素的频率。但是，如果我们有 1 个以上的列表，这可以是额外的工作。让我们讨论执行这项任务的某些方法。

**方法一:利用字典理解+ `set() + count()`**
这是可以执行这个任务的方式之一。在本文中，我们使用 count()和 set()执行计数任务，并且使用字典理解来扩展逻辑。

```py
# Python3 code to demonstrate 
# Elements frequency count in multiple lists
# using set() + count() + dictionary comprehension

# Initializing lists
test_list1 = [1, 3, 2, 4, 5, 1, 2]
test_list2 = [4, 1, 4, 3, 4, 2, 4]
test_list3 = [1, 4, 5, 3, 4, 5, 4]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))
print("The original list 3 is : " + str(test_list3))

# Elements frequency count in multiple lists
# using set() + count() + dictionary comprehension
res = {idx : [test_list1.count(idx), test_list2.count(idx), test_list3.count(idx)]
      for idx in set(test_list1 + test_list2 + test_list3)}

# printing result 
print ("The frequency of each element is : " + str(res))
```

**Output :**

> 原列表 1 为:【1，3，2，4，5，1，2】
> 原列表 2 为:【4，1，4，3，4，2，4】
> 原列表 3 为:【1，4，5，3，4，5，4】
> 每个元素的出现频率为:{1: [2，1，1]，2: [2，1，0]，3: [1，1，1]，4: [1，4，3]，5: [1，0，2]}