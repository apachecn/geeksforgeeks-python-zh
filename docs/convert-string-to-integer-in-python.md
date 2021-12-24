# Python 中字符串转换为整数

> 原文:[https://www . geesforgeks . org/convert-string-to-integer-in-python/](https://www.geeksforgeeks.org/convert-string-to-integer-in-python/)

在 Python 中，可以使用内置的 **`int()`** 函数将字符串转换为整数。int()函数接收任何 [python 数据类型](https://www.geeksforgeeks.org/python-data-types/)，并将其转换为整数。但是使用`int()`功能并不是唯一的方法。这种类型的转换也可以使用 **`float()`** 关键字来完成，因为浮点值可以用整数来计算。

下面是在 python 中将整数转换为字符串的可能方法列表:

**1。使用 [int()功能](https://www.geeksforgeeks.org/python-int-function/)**

> **语法:** int(字符串)

**示例:**

```
num = '10'

# check and print type num variable
print(type(num)) 

# convert the num into string 
converted_num = int(num)

# print type of converted_num
print(type(converted_num))

# We can check by doing some mathematical operations
print(converted_num + 20)
```

作为旁注，要转换为 float，我们可以使用 Python 中的**[【float()】](https://www.geeksforgeeks.org/float-in-python/)**

```
num = '10.5'

# check and print type num variable
print(type(num)) 

# convert the num into string 
converted_num = float(num)

# print type of converted_num
print(type(converted_num))

# We can check by doing some mathematical operations
print(converted_num + 20.5)
```

**2。使用 float()功能**

我们先转换成浮点数，再转换成整数。显然上面的方法更好(直接转换成整数)

> **语法:**浮点(字符串)

 **例:**

```
a = '2'
b = '3'

# print the data type of a and b
print(type(a))
print(type(b))

# convert a using float
a = float(a)

# convert b using int
b = int(b)

# sum both integers
sum = a + b

# as strings and integers can't be added
# try testing the sum
print(sum)
```

**输出:**

```
class 'str'
class 'str'
5.0
```

**注意:**浮点值是可以与整数一起使用进行计算的十进制值。