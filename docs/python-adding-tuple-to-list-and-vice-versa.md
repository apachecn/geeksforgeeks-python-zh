# Python–向列表添加元组，反之亦然

> 原文:[https://www . geesforgeks . org/python-向列表中添加元组-反之亦然/](https://www.geeksforgeeks.org/python-adding-tuple-to-list-and-vice-versa/)

有时，在使用 Python 容器时，我们可能会遇到一个问题，即我们需要执行一个容器与另一个容器的添加。这种问题可能发生在计算机科学和程序设计的许多数据领域。让我们讨论执行这项任务的某些方法。
**方法一:使用+=运算符【列表+元组】**
该运算符可用于将列表与元组连接起来。在内部，它的工作方式类似于 list.extend()的工作方式，在这种情况下，list . extend()可以使用任何 iterable 作为参数，即元组。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Adding Tuple to List and vice - versa
# Using += operator (list + tuple)

# initializing list
test_list = [5, 6, 7]

# printing original list
print("The original list is : " + str(test_list))

# initializing tuple
test_tup = (9, 10)

# Adding Tuple to List and vice - versa
# Using += operator (list + tuple)
test_list += test_tup

# printing result
print("The container after addition : " + str(test_list))
```

**Output : **

```py
The original list is : [5, 6, 7]
The container after addition : [5, 6, 7, 9, 10]
```

**方法#2:使用 tuple()，数据类型转换【tuple+list】**
使用以下技术将 list 添加到 tuple。元组必须转换为列表，列表必须添加，最后结果转换为元组。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Adding Tuple to List and vice - versa
# Using tuple(), data type conversion [tuple + list]

# initializing list
test_list = [5, 6, 7]

# printing original list
print("The original list is : " + str(test_list))

# initializing tuple
test_tup = (9, 10)

# Adding Tuple to List and vice - versa
# Using tuple(), data type conversion [tuple + list]
res = tuple(list(test_tup) + test_list)

# printing result
print("The container after addition : " + str(res))
```

**Output : **

```py
The original list is : [5, 6, 7]
The container after addition : (9, 10, 5, 6, 7)
```