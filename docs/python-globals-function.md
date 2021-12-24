# Python–globals()函数

> 原文:[https://www.geeksforgeeks.org/python-globals-function/](https://www.geeksforgeeks.org/python-globals-function/)

**`globals()`** 函数在 Python 中返回当前全局符号表的字典。

**符号表:**符号表是一种数据结构，包含程序的所有必要信息。这些包括变量名、方法、类等。
全局符号表存储所有与程序全局范围相关的信息，在 Python 中使用 globals()方法进行访问。

不与任何类或函数相关联的函数、变量存储在全局范围内。

```
Syntax: globals()

Parameters: No parameters required.
```

**代码#1:**

```
# Python3 program to demonstrate global() function

# global variable
a = 5

def func():
    c = 10
    d = c + a

    # Calling globals()
    globals()['a'] = d
    print (d)

# Driver Code    
func()
```

**输出:**

```
15

```

**代码#2:**

```
# Python3 program to demonstrate global() function

# global variable
name = 'gautam'

print('Before modification:', name)

# Calling global()
globals()['name'] = 'gautam karakoti'
print('After modification:', name)
```

**输出:**

```
Before modification: gautam
After modification: gautam karakoti

```

**注意:**我们也可以使用 globals()函数来改变全局变量的值。更改后的值也在符号表中更新。