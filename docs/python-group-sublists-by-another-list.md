# Python–按另一个列表分组子列表

> 原文:[https://www . geesforgeks . org/python-group-sublist-by-other-list/](https://www.geeksforgeeks.org/python-group-sublists-by-another-list/)

有时，在处理列表时，我们可能会遇到这样的问题:我们需要将所有的子列表分组，由不同列表中的元素分开。这种类型的自定义分组是不常见的实用程序，但是解决这些问题总是很方便。让我们讨论执行这项任务的特定方式。

**方法#1:使用循环+生成器(yield)**
这是可以执行此任务的蛮力方式。在这种情况下，我们迭代列表，并使用 yield 动态分组。我们跟踪发生的元素，并在第二个列表中找到元素时重新启动列表。

```py
# Python3 code to demonstrate 
# Group Sublists by another List
# using loop + generator(yield)

# helper function
def grp_ele(test_list1, test_list2):
    temp = []
    for i in test_list1: 
        if i in test_list2:
            if temp:  
                yield temp 
                temp = []
            yield i  
        else: 
            temp.append(i)
    if temp: 
        yield temp

# Initializing lists
test_list1 = [8, 5, 9, 11, 3, 7]
test_list2 = [9, 11]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Group Sublists by another List
# using loop + generator(yield)
res = list(grp_ele(test_list1, test_list2))

# printing result 
print ("The Grouped list is : " + str(res))
```

**Output :**

```py
The original list 1 is : [8, 5, 9, 11, 3, 7]
The original list 2 is : [9, 11]
The Grouped list is : [[8, 5], 9, 11, [3, 7]]

```