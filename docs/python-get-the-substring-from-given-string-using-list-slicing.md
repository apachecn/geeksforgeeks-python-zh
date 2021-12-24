# Python |使用列表切片从给定字符串中获取子字符串

> 原文:[https://www . geesforgeks . org/python-从给定字符串中获取子字符串-使用列表切片/](https://www.geeksforgeeks.org/python-get-the-substring-from-given-string-using-list-slicing/)

给定一个字符串，编写一个 Python 程序，使用列表切片从给定的字符串中获取子字符串。让我们用不同的例子来说明这一点。

**代码#1:**

在这个例子中，我们将看到如何从字符串的末尾或开始获取子字符串。

```py
# Python3 code to demonstrate
# to create a substring from a string

# Initialising string
ini_string = 'xbzefdgstb'

# printing initial string and character
print ("initial_strings : ", ini_string)

# creating substring from start of string
# define length upto which substring required
sstring_strt = ini_string[:2]
sstring_end = ini_string[3:]

# printing result
print ("print resultant substring from start", sstring_strt)
print ("print resultant substring from end", sstring_end)
```

**Output:**

```py
initial_strings :  xbzefdgstb
print resultant substring from start xb
print resultant substring from end efdgstb

```

**代码#2:**

在本例中，我们将看到如何通过从特定的位置间隙中获取字符来创建字符串。

```py
# Python3 code to demonstrate
# to create a substring from string

# Initialising string
ini_string = 'xbzefdgstb'

# printing initial string and character
print ("initial_strings : ", ini_string)

# creating substring by taking element
# after certain position gap
# define length upto which substring required
sstring_alt = ini_string[::2]
sstring_gap2 = ini_string[::3]

# printing result
print ("print resultant substring from start", sstring_alt)
print ("print resultant substring from end", sstring_gap2)
```

**Output:**

```py
initial_strings :  xbzefdgstb
print resultant substring from start xzfgt
print resultant substring from end xegb

```

**代码#3:**

在这个例子中，我们考虑了两种情况:从中间取字符串，字符之间有一些位置间隙。

```py
# Python3 code to demonstrate
# to create a substring from string

# Initialising string
ini_string = 'xbzefdgstb'

# printing initial string and character
print ("initial_strings : ", ini_string)

# creating substring by taking element
# after certain position gap
# in defined length
sstring = ini_string[2:7:2]

# printing result
print ("print resultant substring", sstring)
```

**Output:**

```py
initial_strings :  xbzefdgstb
print resultant substring zfg

```