# 从字符串和列表创建元组–Python

> 原文:[https://www . geeksforgeeks . org/从字符串和列表创建元组-python/](https://www.geeksforgeeks.org/create-a-tuple-from-string-and-list-python/)

有时，我们可能会遇到一个问题，我们需要用来自不同容器的元素构建一个新的容器。这种问题可能发生在我们使用不同类型数据的领域。让我们讨论将字符串和列表数据转换为元组的方法。

**方法#1:使用 list 转换为 tuple + `tuple()`**
在该方法中，我们将字符串转换为 List，然后追加到目标列表，然后使用 tuple()将该结果列表转换为 tuple。

```
# Python3 code to demonstrate working of
# Construct tuple from string and list
# using list conversion to tuple + tuple()

# initialize list and string 
test_list = ["gfg", "is"]
test_str = "best"

# printing original list and tuple
print("The original list : " + str(test_list))
print("The original string : " + test_str)

# Construct tuple from string and list
# using list conversion to tuple + tuple()
res = tuple(test_list + [test_str])

# printing result
print("The aggregated tuple is : " + str(res))
```

**Output :**

```
The original list : ['gfg', 'is']
The original string : best
The aggregated tuple is : ('gfg', 'is', 'best')

```