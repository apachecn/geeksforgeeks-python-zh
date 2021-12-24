# Python |不均匀大小列表中的列求和

> 原文:[https://www . geesforgeks . org/python-column-summary-in-everything-list/](https://www.geeksforgeeks.org/python-column-summation-in-uneven-sized-lists/)

与传统的 C 类型矩阵不同，通常的列表列表可以允许可变长度的嵌套列表，当我们需要对其列求和时，不均匀的行长度可能会导致该元素中的某些元素缺失，如果处理不正确，可能会引发异常。让我们讨论以无错误的方式解决这个问题的某些方法。

**方法#1:使用`sum() + filter() + map()` +列表理解**
以上三个函数结合列表理解可以帮助我们执行这个特定的任务，sum 函数有助于执行求和，filter 允许我们检查当前元素，所有行都使用 map 函数进行组合。仅适用于 python 2

```py
# Python code to demonstrate  
# Column summation in uneven sized lists
# using sum() + filter() + map() + list comprehension

# initializing list of lists
test_list = [[1, 5, 3], [4], [9, 8]]

# printing original list 
print ("The original list is : " + str(test_list))

# using sum() + filter() + map() + list comprehension
# Column summation in uneven sized lists
res = [sum(filter(None, j)) for j in map(None, *test_list)]

# printing result
print ("The summation of columns is : " + str(res))
```

**Output :**

```py
The original list is : [[1, 5, 3], [4], [9, 8]]
The summation of columns is : [14, 13, 3]

```