# 关键词

中的 Python

> 原文:[https://www.geeksforgeeks.org/python-in-keyword/](https://www.geeksforgeeks.org/python-in-keyword/)

在编程中，一个关键字是一个“**保留字**”，由语言传达给解释者特殊的含义。它可以是命令或参数。关键字不能在程序段中用作变量名。Python 语言也保留了一些传达特殊含义的关键词。在 Python 中，关键字区分大小写。

#### “在”关键字:

`in`关键字有两个目的:

*   检查列表、元组、范围、字符串等中是否存在值。
*   在 for 循环中迭代一个序列。

**语法:**

```
# Using if statement
if ele in seq:
    statement(s)

# Using for statement
for ele in seq:
    statement(s)

```

**例 1:**

```
# Python program to demonstrate
# in keyword

# Create a lits
animals = ["dog", "lion", "cat"]

# Check if lion in list or not
if "lion" in animals:
    print("Yes")
```

**输出:**

```
Yes

```

**例 2:**

```
# Python program to demonstrate
# in keyword

# Create a string
s = "GeeksforGeeks"

# Iterating through the string
for i in s:

    # if f occurs in the string
    # break the loop
    if i == 'f':
        break

    print(i)
```

**输出:**

```
G
e
e
k
s

```