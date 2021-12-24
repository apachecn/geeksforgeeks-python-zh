# Python |将列表转换为列表列表

> 原文:[https://www . geesforgeks . org/python-convert-list-to-list-of-list/](https://www.geeksforgeeks.org/python-convert-list-into-list-of-lists/)

给定一个字符串列表，编写一个 Python 程序，将给定列表的每个元素转换为一个子列表。因此，将整个列表转换为列表列表。

**示例:**

```
Input : ['alice', 'bob', 'cara']
Output : [['alice'], ['bob'], ['cara']]

Input : [101, 202, 303, 404, 505] 
Output : [[101], [202], [303], [404], [505]]

```

**进场#1 :** 幼稚进场

使用另一个列表“res”和 a 进行循环。使用 Python 的 *split()* 方法，我们以列表本身的形式从列表中提取每个元素，并将其附加到“res”中。最后，返回“res”。这种方法的一个缺点是它不适用于整数列表，因为“int”对象没有属性“split”。

```
# Python3 program to convert 
# list into a list of lists

def extractDigits(lst):
    res = []
    for el in lst:
        sub = el.split(', ')
        res.append(sub)

    return(res)

# Driver code
lst = ['alice', 'bob', 'cara']
print(extractDigits(lst))
```

**Output:**

```
[['alice'], ['bob'], ['cara']]

```

**方法 2 :** 列表理解

列表理解是一种有效的方法，因为它没有利用额外的空间。对于列表中的每个元素“el”，它只是将[el]追加到输出列表中。

```
# Python3 program to convert 
# list into a list of lists

def extractDigits(lst):
    return [[el] for el in lst]

# Driver code
lst = ['alice', 'bob', 'cara']
print(extractDigits(lst))
```

**Output:**

```
[['alice'], ['bob'], ['cara']]

```

**进场#3 :** 巨蟒*地图()*

给定的代码为给定的可迭代“lst”的每个项目映射函数 el:[el]。因此将每个元素作为列表本身输出。

```
# Python3 program to convert 
# list into a list of lists

def extractDigits(lst):
    return list(map(lambda el:[el], lst))

# Driver code
lst = ['alice', 'bob', 'cara']
print(extractDigits(lst))
```

**Output:**

```
[['alice'], ['bob'], ['cara']]

```