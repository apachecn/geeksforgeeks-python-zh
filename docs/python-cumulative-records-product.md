# Python–累积记录产品

> 原文:[https://www . geesforgeks . org/python-累积-记录-产品/](https://www.geeksforgeeks.org/python-cumulative-records-product/)

有时，在处理记录形式的数据时，我们可能会遇到一个问题，即我们需要找到收到的所有记录的产品元素。这是数据科学领域中非常常见的应用。让我们讨论执行这项任务的某些方法。
**方法#1:使用循环+生成器表达式**
这是实现解决这个任务最基本的方法。在本文中，我们使用生成器表达式迭代整个嵌套列表，并使用显式乘积函数获得乘积元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cumulative Records Product
# using loop + generator expression

# getting Product
def prod(val) :
    res = 1
    for ele in val:
        res *= ele
    return res

# initialize list
test_list = [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]

# printing original list
print("The original list : " + str(test_list))

# Cumulative Records Product
# using loop + generator expression
res = prod(int(j) for i in test_list for j in i)

# printing result
print("The Cumulative product of list is : " + str(res))
```

**Output**

```py
The original list : [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]
The Cumulative product of list is : 5644800

```

**方法 2:使用 loop+map()+chain . from _ iterable()**
以上方法的组合也可以用来执行这个任务。在这种情况下，通过 map()和 from_iterable()的组合来扩展查找乘积。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cumulative Records Product
# using product + map() + chain.from_iterable()
from itertools import chain

# getting Product
def prod(val) :
    res = 1
    for ele in val:
        res *= ele
    return res

# initialize list
test_list = [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]

# printing original list
print("The original list : " + str(test_list))

# Cumulative Records Product
# using product + map() + chain.from_iterable()
res = prod(map(int, chain.from_iterable(test_list)))

# printing result
print("The cumulative product of list is : " + str(res))
```

**Output**

```py
The original list : [(2, 4), (6, 7), (5, 1), (6, 10), (8, 7)]
The cumulative product of list is : 5644800

```