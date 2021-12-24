# Python |将列表转换为 Python 数组

> 原文:[https://www . geesforgeks . org/python-convert-list-to-python-array/](https://www.geeksforgeeks.org/python-convert-list-to-python-array/)

有时，在 Python 中工作时，我们可能会遇到这样的问题:我们需要将数据元素限制为只有一种类型。列表，可以是异构的，可以有多个数据类型的数据，这有时是不可取的。需要将其转换为限制数据类型的数据结构。Python 语言附带了可用于此目的的数组数据结构。让我们讨论一种将列表转换为数组的方法。

**方法:使用`array()` +数据类型指示器**
使用`array()`可以轻松执行该任务。这是 Python 中转换为数组的内置函数。数据类型指示器“I”用于限制数据类型的整数。

```py
# Python3 code to demonstrate working of
# Convert list to Python array
# Using array() + data type indicator
from array import array

# initializing list
test_list = [6, 4, 8, 9, 10]

# printing list
print("The original list : " + str(test_list))

# Convert list to Python array
# Using array() + data type indicator
res = array("i", test_list)

# Printing result
print("List after conversion to array : " + str(res))
```

**Output :**

```py

The original list : [6, 4, 8, 9, 10]
List after conversion to array : array('i', [6, 4, 8, 9, 10])

```