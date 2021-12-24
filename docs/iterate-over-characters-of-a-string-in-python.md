# 在 Python 中迭代字符串的字符

> 原文:[https://www . geesforgeks . org/iterate-over-of-characters-of-a-string-in-python/](https://www.geeksforgeeks.org/iterate-over-characters-of-a-string-in-python/)

在 Python 中，使用 String 操作时，可以对其进行多种操作。让我们看看如何在 Python 中迭代字符串的字符。

**示例#1:** 使用简单迭代和`range()`

```py
# Python program to iterate over characters of a string

# Code #1
string_name = "geeksforgeeks"

# Iterate over the string
for element in string_name:
    print(element, end=' ')
print("\n")

# Code #2
string_name = "GEEKS"

# Iterate over index
for element in range(0, len(string_name)):
    print(string_name[element])
```

**输出:**

```py
g e e k s f o r g e e k s 

G
E
E
K
S

```