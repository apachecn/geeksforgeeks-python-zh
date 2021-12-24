# Python 中字符串第一个字符如何大写

> 原文:[https://www . geeksforgeeks . org/如何在 python 中大写字符串的第一个字符/](https://www.geeksforgeeks.org/how-to-capitalize-first-character-of-string-in-python/)

字符串大小写改变的问题很常见，已经讨论过很多次了。有时，我们可能会遇到这样的问题，我们需要将字符串的初始字符转换为大写。让我们讨论一下实现这一点的某些方法。

**方法#1:使用字符串切片+ `upper()`**
这个任务可以很容易地使用大写方法来执行，该方法将提供给它的字符大写，切片可以用来在小写的第一个字符之后添加剩余的字符串。

```py
# Python3 code to demonstrate working of
# Initial character upper case
# Using upper() + string slicing

# initializing string 
test_str = "geeksforgeeks"

# printing original string 
print("The original string is : " + str(test_str))

# Using upper() + string slicing
# Initial character upper case
res = test_str[0].upper() + test_str[1:]

# printing result 
print("The string after uppercasing initial character : " + str(res))
```

**Output :**

```py
The original string is : geeksforgeeks
The string after uppercasing initial character : Geeksforgeeks

```