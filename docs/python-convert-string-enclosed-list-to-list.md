# Python |将字符串括起来的列表转换为列表

> 原文:[https://www . geesforgeks . org/python-convert-string-括起来-list-to-list/](https://www.geeksforgeeks.org/python-convert-string-enclosed-list-to-list/)

给定一个包含在字符串(或引号)中的列表，编写一个 Python 程序将给定的字符串转换为列表类型。

**示例:**

```
Input : "[0, 2, 9, 4, 8]"
Output : [0, 2, 9, 4, 8]

Input : "['x', 'y', 'z']"
Output : ['x', 'y', 'z']

```

**接近#1 :** 巨蟒`eval()`

`eval()`方法解析传递给该方法的表达式，并在程序中运行 python 表达式(代码)。这里，它将包含在引号中的列表作为表达式并运行它，最后返回列表。

```
# Python3 program to ways to convert 
# list enclosed within string to list

def convert(lst):
    return eval(lst)

# Driver code
lst = "[0, 2, 9, 4, 8]"
print(convert(lst))
```

**Output:**

```
[0, 2, 9, 4, 8]

```

**使用`literal_eval()`接近#2 :**

*literal_eval()* 函数的工作原理与`eval()`相同，唯一的区别是，如果输入不是有效的 Python 数据类型，它会引发异常，代码不会被执行。

```
# Python3 program to ways to convert 
# list enclosed within string to list
from ast import literal_eval

def convert(lst):
    return literal_eval(lst)

# Driver code
lst = "[0, 2, 9, 4, 8]"
print(convert(lst))
```

**Output:**

```
[0, 2, 9, 4, 8]

```

**使用`json.loads()`接近#3 :**

```
# Python3 program to ways to convert 
# list enclosed within string to list
from json import loads

def convert(lst):
    return loads(lst)

# Driver code
lst = "[0, 2, 9, 4, 8]"
print(convert(lst))
```

**Output:**

```
[0, 2, 9, 4, 8]

```