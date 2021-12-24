# Python |在列表中所有项目的开头插入字符串

> 原文:[https://www . geesforgeks . org/python-在列表中所有项目的开头插入字符串/](https://www.geeksforgeeks.org/python-insert-the-string-at-the-beginning-of-all-items-in-a-list/)

给定一个列表，编写一个 Python 程序，在列表中所有项目的开头插入一些字符串。

**示例:**

```py
Input : list = [1, 2, 3, 4], str = 'Geek'
Output : list = ['Geek1', 'Geek2', 'Geek3', 'Geek4']

Input : list = ['A', 'B', 'C'], str = 'Team'
Output : list = ['TeamA', 'TeamB', 'TeamC']

```

有多种方法可以将字符串插入列表中所有项目的开头。

**方法#1:使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**
列表理解是定义和创建列表的优雅方式。它还可以用于将表达式应用于序列中的每个元素。我们可以使用`format()`功能，该功能允许多次替换和值格式化。

```py
# Python3 program to insert the string 
# at the beginning of all items in a list
def prepend(list, str):

    # Using format()
    str += '{0}'
    list = [str.format(i) for i in list]
    return(list)

# Driver function
list = [1, 2, 3, 4]
str = 'Geek'
print(prepend(list, str))
```

**输出:**

```py
['Geek1', 'Geek2', 'Geek3', 'Geek4']
```

列表理解中的另一种方法是用“%”代替 format()函数

```py
# Using '% s'
str += '% s'
list =  [str % i for i in list]
```

**方法 2:使用内置`map()`功能**
另一种方法是使用 map()功能。该函数将列表中所有项目的开头映射到字符串。

```py
# Python3 program to insert the string 
# at the beginning of all items in a list
def prepend(List, str):

    # Using format()
    str += '{0}'
    List = ((map(str.format, List)))
    return List

# Driver function
list = [1, 2, 3, 4]
str = 'Geek'
print(prepend(list, str))
```

**输出:**

```py
['Geek1', 'Geek2', 'Geek3', 'Geek4']
```