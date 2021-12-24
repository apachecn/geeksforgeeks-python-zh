# Python–将不平衡列表转换为记录

> 原文:[https://www . geeksforgeeks . org/python-convert-凹凸列表-转化为记录/](https://www.geeksforgeeks.org/python-convert-uneven-lists-into-records/)

有时，在使用记录时，我们可能会遇到一个问题，一个列表中有键，另一个列表中有值。但有时，值可以是多个有序的，比如特定科目的分数或分数。这类问题可能发生在学校编程和开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用字典理解+ `enumerate()` +列表切片**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用字典理解进行迭代，并通过切片提取记录值来枚举和形成期望的结果。

```py
# Python3 code to demonstrate working of 
# Convert Uneven Lists into Records
# Using dictionary comprehension + enumerate() + list slicing

# initializing lists
test_list1 = ['Nikhil', 'Akash', 'Akshat']
test_list2 = [5, 6, 7, 8, 2, 3, 12, 2, 10]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Convert Uneven Lists into Records
# Using dictionary comprehension + enumerate() + list slicing
temp = len(test_list2) // len(test_list1)
res = {key: test_list2[idx :: temp] for idx, key in enumerate(test_list1)}

# printing result 
print("The paired data dictionary : " + str(res)) 
```

**Output :**

> 原列表 1 为:['Nikhil '，' Akash '，' Akshat']
> 原列表 2 为:【5，6，7，8，2，3，12，2，10】
> 配对数据字典:{'Nikhil': [5，8，12]，' Akshat': [7，3，10]，' Akash': [6，2，2]}