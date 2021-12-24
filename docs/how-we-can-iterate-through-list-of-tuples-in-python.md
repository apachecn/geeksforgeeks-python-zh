# 如何在 Python 中遍历元组列表

> 原文:[https://www . geeksforgeeks . org/我们如何在 python 中迭代元组列表/](https://www.geeksforgeeks.org/how-we-can-iterate-through-list-of-tuples-in-python/)

在本文中，我们将讨论在 Python 中迭代元组列表的不同方法。

**可以这样做:**

*   使用循环。
*   使用枚举()。

## 方法一:使用[循环](https://www.geeksforgeeks.org/loops-in-python/)

这里我们将形成一个用于循环的元组列表。

## 蟒蛇 3

```py
# create a list of tuples with student
# details
name = [('sravan',7058,98.45),
        ('ojaswi',7059,90.67),
        ('bobby',7060,78.90),
        ('rohith',7081,67.89),
        ('gnanesh',7084,98.01)]

# iterate using for loop
for x in name:

  # iterate in each tuple element
  for y in x:
      print(y)

  print()
```

**输出:**

```py
sravan
7058
98.45

ojaswi
7059
90.67

bobby
7060
78.9

rohith
7081
67.89

gnanesh
7084
98.01
```

## 方法二:使用[枚举()](https://www.geeksforgeeks.org/enumerate-in-python/)

这里我们将使用 enumerate()函数迭代元组列表。很多时候，在处理迭代器时，我们也需要记录迭代次数。Python 通过为这个任务提供一个内置函数 enumerate()来简化程序员的任务。枚举()方法向 iterable 添加计数器，并以枚举对象的形式返回它。然后，这个枚举对象可以直接在 for 循环中使用，或者使用 list()方法转换为元组列表。

> **语法:**枚举(可迭代，开始=0)
> 
> **参数:**
> 
> *   **可迭代:**任何支持迭代的对象
> *   **开始:**计数器开始的索引值，默认为 0

## 蟒蛇 3

```py
# create a list of tuples with with atudent
# details
name = [('sravan',7058,98.45),
        ('ojaswi',7059,90.67),
        ('bobby',7060,78.90),
        ('rohith',7081,67.89),
        ('gnanesh',7084,98.01)]
l = []

# iterate using index with enumerate function
for index, tuple in enumerate(name):

    # access through index
      # by appending to list
    l.append(name[index])

# iterate through the list
for x in l:
    for y in x:
       print(y)
    print()
```

**输出:**

```py
sravan
7058
98.45

ojaswi
7059
90.67

bobby
7060
78.9

rohith
7081
67.89

gnanesh
7084
98.01
```