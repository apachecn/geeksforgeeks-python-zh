# Python |将列表转换为元组

> 原文:[https://www . geesforgeks . org/python-将列表转换为元组/](https://www.geeksforgeeks.org/python-convert-a-list-into-a-tuple/)

给定一个列表，编写一个 Python 程序，将给定的列表转换成元组。

**示例:**

```
Input : [1, 2, 3, 4]
Output : (1, 2, 3, 4)

Input : ['a', 'b', 'c']
Output : ('a', 'b', 'c')

```

**使用`tuple(list_name)`接近#1 :** 。

简单地使用 tuple(list_name)就可以完成对 tuple 的类型转换。

```
# Python3 program to convert a 
# list into a tuple
def convert(list):
    return tuple(list)

# Driver function
list = [1, 2, 3, 4]
print(convert(list))
```

**Output:**

```
(1, 2, 3, 4)

```

**方法 2 :**
上述方法的一个小变化是在`tuple()`内部使用一个循环。

```
# Python3 program to convert a 
# list into a tuple
def convert(list):
    return tuple(i for i in list)

# Driver function
list = [1, 2, 3, 4]
print(convert(list))
```

**Output:**

```
(1, 2, 3, 4)

```

**方法#3 :** 使用`(*list, )`
这实际上是将列表 l 解包到元组文本中，该元组文本是由于单个逗号(，)的存在而创建的。这种方法速度稍快，但可读性较差。

```
# Python3 program to convert a 
# list into a tuple
def convert(list):
    return (*list, )

# Driver function
list = [1, 2, 3, 4]
print(convert(list))
```

**Output:**

```
(1, 2, 3, 4)

```