# 在 Python 中将字符串转换为数字，将数字转换为字符串

> 原文:[https://www . geesforgeks . org/convert-string-to-numbers-and-numbers-to-string-in-python/](https://www.geeksforgeeks.org/convert-strings-to-numbers-and-numbers-to-strings-in-python/)

在 Python 中，[字符串](https://www.geeksforgeeks.org/python-strings/)或数字可以使用各种内置函数转换为多个字符串，如 [str()](https://www.geeksforgeeks.org/python-str-function/) 、 [int()](https://www.geeksforgeeks.org/python-int-function/) 、 [float()](https://www.geeksforgeeks.org/float-in-python/) 等。让我们看看如何使用它们。

**示例 1:** 将 Python 字符串转换为 int:

## 蟒蛇 3

```
# code
# gfg contains string 10
gfg = "10"

# using the int(), string is auto converted to int
print(int(gfg)+20)
```

**输出:**

```
30
```

**示例 2:** 将 Python 字符串转换为浮点:

## 蟒蛇 3

```
# code
gfg = "10"

# float(gfg) gives 10.0
print(float(gfg)+2.0)
```

**输出:**

```
12.0
```

**示例 3:** 将 Python int 转换为字符串:

这是通过使用如下所示的 [str()](https://www.geeksforgeeks.org/python-str-function/) 功能来实现的

## 蟒蛇 3

```
# code
gfg = 100

# str(gfg) gives '100'
print(str(gfg)+" is a 3 digit number")

# concatenation is performed between them
print(str(gfg)+"200")
```

**输出:**

```
100 is a 3 digit number
100200
```

**示例 4:** 将 Python 浮点转换为字符串

这是通过使用如下所示的 [str()](str()) 功能来实现的

## 蟒蛇 3

```
# code
gfg = 20.0

# str(gfg) becomes '20.0'
print(str(gfg)+"is now a string")

# no addition is performed. concatenated output
print(str(gfg)+"30.0")
```

**输出:**

```
20.0is now a string
20.030.0
```