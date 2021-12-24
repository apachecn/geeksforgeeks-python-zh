# 在 Python 中将字符串转换为长整型

> 原文:[https://www . geesforgeks . org/convert-string-to-long-in-python/](https://www.geeksforgeeks.org/convert-string-to-long-in-python/)

Python 定义了类型转换函数，直接将一种数据类型转换成另一种数据类型。本文旨在提供关于将字符串转换为长字符串的信息。

## 将字符串转换为长字符串

long 是长度不限的整型值。通过将字符串转换为 long，我们将字符串类型的值转换为 long 类型。在 Python3 中，int 默认升级为 long，这意味着所有整数在 Python3 中都是 long。所以我们可以使用 [int()](https://www.geeksforgeeks.org/python-int-function/) 在 Python 中将字符串转换为 long。

**语法:**

```py
int(string, base)
```

**参数:**

```py
string : consists of 1's and 0's
base : (integer value) base of the number.example 1
```

**例 1:**

## 蟒蛇 3

```py
a_string = "123"
print(type(a_string))

# Converting to long
a_long = int(a_string)
print(a_long)
print(type(a_long))
```

**输出:**

```py
<class 'str'>
123
<class 'int'>
```

**例 2:**

## 蟒蛇 3

```py
a='0x'
arr0 = '00000018000004000000000000000000'
arr1 = '00000000000000000000000000000000'
arr2 = 'fe000000000000000000000000000000'
arr3 = '00000000000000000000000000ffffff'
data = a+arr0+arr1+arr2+arr3
print(data)
print(type(data))

# Converting to long
data1 = int(data, 16)
print(type(data1))
```

**输出:**

> 0x 000001800000400000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000