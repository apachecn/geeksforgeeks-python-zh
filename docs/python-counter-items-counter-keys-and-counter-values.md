# Python–计数器项目()、计数器键()和计数器值()

> 原文:[https://www . geesforgeks . org/python-counter-items-counter-key-and-counter-values/](https://www.geeksforgeeks.org/python-counter-items-counter-keys-and-counter-values/)

计数器类是 Python3 中集合模块提供的一种特殊类型的对象数据集。集合模块为用户提供了专门的容器数据类型，从而为 Python 的通用内置功能(如字典、列表和元组)提供了一种替代方案。Counter 是一个子类，用于计数 hashable 对象。它在被调用时隐式地创建一个 iterable 的哈希表。

## Counter.items()

Counter.items()方法有助于查看列表的元素以及它们在元组中各自的频率。

> **语法:** Counter.items()
> **参数:** None
> **返回:**class dict _ items 的对象

**例:**

## 蟒蛇 3

```py
# importing the module
from collections import Counter

# making a list
list = [1, 1, 2, 3, 4, 5,
        6, 7, 9, 2, 3, 4, 8]

# instantiating a Counter object
ob = Counter(list)

# Counter.items()
items = ob.items()

print("The datatype is "
      + str(type(items)))

# displaying the dict_items
print(items)

# iterating over the dict_items
for i in items:
    print(i)
```

**输出:**

> 数据类型为
> dict_items([(1，2)、(2，2)、(3，2)、(4，2)、(5，1)、(6，1)、(7，1)、(9，1)、(8，1)])
> (1，2)
> (2，2)
> (3，2)
> (4，2)
> (5，1)
> (6，1)
> (7，1)
> (9，1)
> (8，1)

## 计数器键()

Counter.keys()方法有助于查看列表中的唯一元素。

> **语法:** Counter.keys()
> **参数:** None
> **返回:**class dict _ items 的对象

**例:**

## 蟒蛇 3

```py
# importing the module
from collections import Counter

# making a list
list = [1, 1, 2, 3, 4, 5,
        6, 7, 9, 2, 3, 4, 8]

# instantiating a Counter object
ob = Counter(list)

# Counter.keys()
keys = ob.keys()

print("The datatype is "
      + str(type(keys)))

# displaying the dict_items
print(keys)

# iterating over the dict_items
for i in keys:
    print(i)
```

**输出:**

> 数据类型为
> dict_keys([1，2，3，4，5，6，7，9，8])
> 1
> 2
> 3
> 4
> 5
> 6
> 7
> 9
> 8

## 计数器值()

Counter.values()方法有助于查看每个唯一元素的频率。

> **语法:** Counter.values()
> **参数:** None
> **返回:**class dict _ items 的对象

**例:**

## 蟒蛇 3

```py
# importing the module
from collections import Counter

# making a list
list = [1, 1, 2, 3, 4, 5,
        6, 7, 9, 2, 3, 4, 8]

# instantiating a Counter object
ob = Counter(list)

# Counter.values()
values = ob.values()

print("The datatype is "
      + str(type(values)))

# displaying the dict_items
print(values)

# iterating over the dict_items
for i in values:
    print(i)
```

**输出:**

> 数据类型为
> dict_values([2，2，2，2，1，1，1，1])
> 2
> 2
> 2
> 2
> 1
> 1
> 1
> 1
> 1