# Python |检查列表是否为矩阵

> 原文:[https://www . geesforgeks . org/python-check-if-list-is-matix/](https://www.geeksforgeeks.org/python-check-if-list-is-matix/)

有时，在使用 Python 列表时，我们可能会遇到需要检查矩阵的问题。由于矩阵的广泛使用，这类问题在数据科学领域可能会有应用。让我们讨论一种可以用来完成这项任务的技巧和速记。
**方法:使用 isinstance() + all()**
这个问题可以使用以上函数的组合来执行。all()可用于检查列表的所有元素，isinstance 函数检查列表中的列表数据类型。背后的逻辑是，列表的每个元素都必须是一个列表，才能将其限定为矩阵。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Check if list is Matrix
# using isinstance() + all()

# initialize lists
test_list = [[4, 5], [5, 8], [9, 10]]

# printing original list
print("The original list is : " + str(test_list))

# Check if list is Matrix
# using isinstance() + all()
res = all(isinstance(ele, list) for ele in test_list)

# printing result
print("Is list a Matrix ?: " + str(res))
```

**Output : **

```py
The original list is : [[4, 5], [5, 8], [9, 10]]
Is list a Matrix ?: True
```