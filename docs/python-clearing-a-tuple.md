# Python–清除元组

> 原文:[https://www.geeksforgeeks.org/python-clearing-a-tuple/](https://www.geeksforgeeks.org/python-clearing-a-tuple/)

有时，在处理记录数据时，我们可能会遇到要求清除数据记录的问题。元组是不可变的，不能修改，因此使这项工作变得困难。让我们讨论执行这项任务的某些方法。
**方法#1:使用 list() + clear() + tuple()**
以上 3 个函数的组合可以用来执行这个任务。在这种情况下，我们将元组相互转换为列表，清除它，并再次使用元组()转换为元组。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Clearing a tuple
# using list() + tuple() + clear()

# initializing tuple
test_tup = (1, 5, 3, 6, 8)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Clearing a tuple
# using list() + tuple() + clear()
temp = list(test_tup)
temp.clear()
test_tup = tuple(temp)

# print result
print("The tuple after clearing values : " + str(test_tup))
```

**Output : **

```py
The original tuple : (1, 5, 3, 6, 8)
The tuple after clearing values : ()
```

**方法#2:使用 tuple()重新初始化】**
执行此任务的另一种直接方法是使用 tuple()重新初始化 tuple，这将返回空 tuple。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Clearing a tuple
# using Reinitialization + tuple()

# initializing tuple
test_tup = (1, 5, 3, 6, 8)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Clearing a tuple
# using Reinitialization + tuple()
test_tup = tuple()

# print result
print("The tuple after clearing values : " + str(test_tup))
```

**Output : **

```py
The original tuple : (1, 5, 3, 6, 8)
The tuple after clearing values : ()
```