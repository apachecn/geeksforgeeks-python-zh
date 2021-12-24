# 如何在 Python 中替换列表中的值？

> 原文:[https://www . geesforgeks . org/如何替换 python 列表中的值/](https://www.geeksforgeeks.org/how-to-replace-values-in-a-list-in-python/)

在本文中，我们将看到如何使用 Python 替换列表中的值。我们可以用几种方法替换列表中的值。以下是替换列表中值的方法。

*   使用列表索引
*   用于循环
*   使用 while 循环
*   使用 lambda 函数
*   使用列表切片

## 方法一:使用[列表索引](https://www.geeksforgeeks.org/python-list/)

我们可以使用索引来访问列表中的项目。这是在 python 中替换列表中的值的最简单和最容易的方法。如果我们想替换列表的第一项，我们可以使用索引 0。在下面，索引是我们想要替换的项目的索引，new_value 是应该替换列表中旧值的值。

> **语法:**l[索引]=new_value

**代码:**

## 蟒蛇 3

```py
# Replace Values in a List using indexing

# define list
l = [ 'Hardik','Rohit', 'Rahul', 'Virat', 'Pant']

# replace first value
l[0] = 'Shardul'

# print list
print(l)
```

**输出:**

```py
['Shardul', 'Rohit', 'Rahul', 'Virat', 'Pant']
```

## 方法二:使用[进行循环](https://www.geeksforgeeks.org/python-for-loops/)

我们可以使用 for 循环遍历列表并替换列表中的值。假设我们想把列表中的“哈迪克”和“潘特”替换为“夏杜尔”和“伊山”。我们首先使用 for 循环和 if 条件在列表中查找值，然后用新值替换它。

## 蟒蛇 3

```py
# Replace Values in a List using For Loop

# define list
l = ['Hardik', 'Rohit', 'Rahul', 'Virat', 'Pant']

for i in range(len(l)):

    # replace hardik with shardul
    if l[i] == 'Hardik':
        l[i] = 'Shardul'

    # replace pant with ishan
    if l[i] == 'Pant':
        l[i] = 'Ishan'

# print list
print(l)
```

**输出:**

```py
['Shardul', 'Rohit', 'Rahul', 'Virat', 'Ishan']
```

## 方法三:使用[同时循环](https://www.geeksforgeeks.org/python-while-loop/)

我们还可以使用 while 循环来替换列表中的值。而循环的作用与循环相同。在 while 循环中，我们首先定义一个值为 0 的变量，然后遍历列表。如果值与我们想要替换的值匹配，那么我们用新值替换它。

## 蟒蛇 3

```py
# Replace Values in a List using While Loop

# define list
l = ['Hardik', 'Rohit', 'Rahul', 'Virat', 'Pant']

i = 0
while i < len(l):

    # replace hardik with shardul
    if l[i] == 'Hardik':
        l[i] = 'Shardul'

    # replace pant with ishan
    if l[i] == 'Pant':
        l[i] = 'Ishan'

    i += 1

# print list
print(l)
```

**输出:**

```py
['Shardul', 'Rohit', 'Rahul', 'Virat', 'Ishan']
```

## 方法四:使用[λ函数](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

在这个方法中，我们使用 lambda 和 map 函数来替换列表中的值。map()是 python 中的一个内置函数，用于迭代一个列表，而不使用任何循环语句。lambda 是 python 中包含单行表达式的匿名函数。这里我们给出了一个表达式作为替换值的条件。在这里，我们将λ函数中的“潘特”替换为“伊山”。然后使用 list()函数，我们将地图对象转换为列表。

> **语法:**l = list(map(lambda x:x . replace(' old _ value '，' new_value ')，l))

## 蟒蛇 3

```py
# Replace Values in a List using Lambda Function

# define list
l = ['Hardik', 'Rohit', 'Rahul', 'Virat', 'Pant']

# replace Pant with Ishan
l = list(map(lambda x: x.replace('Pant', 'Ishan'), l))

# print list
print(l)
```

**输出:**

```py
['Hardik', 'Rohit', 'Rahul', 'Virat', 'Ishan']
```

## 方法五:使用[列表切片](https://www.geeksforgeeks.org/python-list-slicing/)

Python 允许我们在列表中进行切片。切片使我们能够访问列表的某些部分。我们可以使用切片来替换列表中的值。首先，我们找到要替换的变量的索引，并将其存储在变量“I”中。然后，我们使用列表切片将该项目替换为新值。假设我们想用“Shikhar”替换“Rahul”，那么我们首先找到“Rahul”的索引，然后进行列表切片，删除“Rahul”并在该位置添加“Shikhar”。

> **语法:**l = l[:index]+[' new _ value ']+l[index+1:]

## 蟒蛇 3

```py
# Replace Values in a List using Slicing

# define list
l = ['Hardik', 'Rohit', 'Rahul', 'Virat', 'Pant']

# find the index of Rahul
i = l.index('Rahul')

# replace Rahul with Shikhar
l = l[:i]+['Shikhar']+l[i+1:]

# print list
print(l)
```

**输出:**

```py
['Hardik', 'Rohit', 'Shikhar', 'Virat', 'Pant']
```