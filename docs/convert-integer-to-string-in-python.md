# Python 中整数转换为字符串

> 原文:[https://www . geesforgeks . org/convert-integer-to-string-in-python/](https://www.geeksforgeeks.org/convert-integer-to-string-in-python/)

在 Python 中，可以使用内置的 **str()** 函数将整数转换为字符串。str()函数接收任何 [python 数据类型](https://www.geeksforgeeks.org/python-data-types/)，并将其转换为字符串。但是使用 [**str()**](https://www.geeksforgeeks.org/str-vs-repr-in-python/) 并不是唯一的方法。这种类型的转换也可以使用[**“% s”**](https://www.geeksforgeeks.org/string-formatting-in-python-using/)关键字、 [**来完成。格式化**](https://www.geeksforgeeks.org/python-format-function/) 功能或使用 [**f-string**](https://www.geeksforgeeks.org/formatted-string-literals-f-strings-python/) 功能。
下面是在 python 中将整数转换为字符串的可能方法列表:

**1。使用 str()功能**

> **语法:**字符串(整数值)

**示例:**

## 蟒蛇 3

```
num = 10

# check  and print type of num variable
print(type(num))

# convert the num into string
converted_num = str(num)

# check  and print type converted_num variable
print(type(converted_num))
```

**2。使用“%s”关键字**

> **语法:**% s %整数

**示例:**

## 蟒蛇 3

```
num = 10

# check  and print type of num variable
print(type(num))

# convert the num into string and print
converted_num = "% s" % num
print(type(converted_num))
```

**3。使用。格式()功能**

> **语法:**“{ }”。格式(整数)

**示例:**

## 蟒蛇 3

```
num = 10

# check  and print type of num variable
print(type(num))

# convert the num into string and print
converted_num = "{}".format(num)
print(type(converted_num))
```

**4。使用 f 弦**

> **语法:**f“{整数}”

**示例:**

## 蟒蛇 3

```
num = 10

# check  and print type of num variable
print(type(num))

# convert the num into string
converted_num = f'{num}'

# print type of converted_num
print(type(converted_num))
```