# python 3 中不同的输入和输出技术

> 原文:[https://www . geesforgeks . org/different-input-and-output-technologies-in-pyt 3/](https://www.geeksforgeeks.org/different-input-and-output-techniques-in-python3/)

在本文中，我们将学习一些基本的输入输出技术，在这些技术的帮助下，我们可以很容易地遵循我们在日常编码生活或竞争性编程中面临的问题中提到的输入和输出格式。

## **输入技术**

**1。** **单次输入:**Python 中的单次输入可以使用 [input()](https://www.geeksforgeeks.org/taking-input-in-python/) 方法进行。

**示例:**

## 蟒蛇 3

```py
# For integers
n = int(input())

# For floating or decimal numbers
n = float(input())

# For Strings
n = input()
```

**2。采取多项输入:**借助[地图()](https://www.geeksforgeeks.org/python-map-function/)和 [split()](https://www.geeksforgeeks.org/python-string-split/) 方法可以采取 Python 中的多项输入。split()方法拆分用空格分隔的输入并返回一个 iterable，而当这个函数与 map()函数一起使用时，它可以相应地将输入转换为 float 和 int。

**例:**

## 蟒 3

```py
# For Strings
x, y = input().split()

# For integers and floating point
# numbers
m, n = map(int, input().split()) 
m, n = map(float, input().split())
```

**3。将可变数量的输入作为列表或元组:**为此，可以使用 split()和 map()函数。当这些函数返回一个 iterable 时，我们可以相应地将给定的 iterable 转换为列表、元组或集合。

**示例:**

## 蟒蛇 3

```py
# For Input - 4 5 6 1 56 21 
# (Space separated inputs)
n = list(map(int, input().split()))
print(n)
```

**输出:**

```py
[4, 5, 6, 1, 56, 21]

```

**4。取固定和可变输入数:**

## 蟒 3

```py
# Input: geeksforgeeks 2 0 2 0
str, *lst = input().split()
lst = list(map(int, lst))

print(str, lst)
```

**输出:**

```py
geeksforgeeks [2, 0, 2, 0]
```

## 输出技术

**1。不同行上的输出:** [print()](https://www.geeksforgeeks.org/python-output-using-print-function/) 方法在 python 中用于打印到控制台。

**例:**

## 蟒 3

```py
lst = ['geeks', 'for', 'geeks']

for i in lst:
    print(i)
```

**输出:**

```py
geeks
for
geeks

```

**2。同一行输出:**[Python 中的结束参数](https://www.geeksforgeeks.org/gfact-50-python-end-parameter-in-print/)可用于同一行打印。

**例 1:**

## 蟒 3

```py
lst = ['geeks', 'for', 'geeks']

for i in lst:
    print(i, end='')
```

**输出:**

```py
geeksforgeeks
```

**例 2:** 用空格打印。

## 蟒 3

```py
lst = ['geeks', 'for', 'geeks']

for i in lst:
    print(i,end=' ')
```

**输出:**

```py
geeks for geeks

```

**3。输出格式化:**如果你想格式化你的输出，你可以使用{}和 format()函数。{}是以()格式提供的变量的占位符，就像我们在 C 编程中的%d 一样。

**例:**

## 蟒 3

```py
print('I love {}'.format('geeksforgeeks.'))

print("I love {0} {1}".format('Python', 'programming.')
```

**输出:**

```py
I love geeksforgeeks.
I love Python programming.

```

**注意:**格式化整数或浮点数时，可以在{}中使用原始方法。比如“{ 5.2f }”或者用数字我们可以把它写成“{0:5.2f}”。我们还可以使用字符串模块“%”运算符来格式化我们的输出。