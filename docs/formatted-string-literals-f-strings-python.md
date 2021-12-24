# Python 中的 f 字符串

> 原文:[https://www . geeksforgeeks . org/formated-string-常值-f-strings-python/](https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/)

[PEP 498](https://docs.python.org/3/whatsnew/3.6.html#whatsnew36-pep498) 引入了一种新的字符串格式化机制，称为*文字字符串插值*或更常见的 *F 字符串*(因为字符串文字前面有前导 *f* 字符)。f-strings 背后的思想是使字符串插值更简单。
要创建 f 字符串，请在字符串前面加上字母“f”。字符串本身的格式化方式与您使用 [str.format()](https://www.geeksforgeeks.org/python-format-function/) 的方式非常相似。F-strings 提供了一种简洁方便的方法，可以将 python 表达式嵌入到字符串文字中进行格式化。

**代码#1 :**

## 蟒蛇 3

```py
# Python3 program introducing f-string
val = 'Geeks'
print(f"{val}for{val} is a portal for {val}.")

name = 'Tushar'
age = 23
print(f"Hello, My name is {name} and I'm {age} years old.")
```

**输出:**

```py
GeeksforGeeks is a portal for Geeks.
Hello, My name is Tushar and I'm 23 years old.
```

**代码#2 :**

## 蟒蛇 3

```py
# Prints today's date with help
# of datetime library
import datetime

today = datetime.datetime.today()
print(f"{today:%B %d, %Y}")
```

**输出:**

```py
April 04, 2018
```

**注意:**F-string 比最常用的两种字符串格式化机制，即% formatting 和 str.format()更快。

让我们看几个错误示例，在使用 f-string 时可能会出现:
**代码#3 :** 演示语法错误。

## 蟒蛇 3

```py
answer = 456
f"Your answer is "{answer}""
```

**代码#4 :** 反斜杠不能直接用于格式字符串。

## 蟒蛇 3

```py
f"newline: {ord('\n')}"
```

**输出:**

```py
Traceback (most recent call last):
  Python Shell, prompt 29, line 1
Syntax Error: f-string expression part cannot include a backslash: , line 1, pos 0
```

但是文档指出，我们可以将反斜杠放入变量中作为变通方法:

## 蟒蛇 3

```py
newline = ord('\n')

f"newline: {newline}"
```

**输出:**

```py
newline: 10
```

**参考:**T2【PEP】498，文字串插值 T4】