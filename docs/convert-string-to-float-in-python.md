# 在 Python 中将字符串转换为浮点数

> 原文:[https://www . geesforgeks . org/convert-string-to-float-in-python/](https://www.geeksforgeeks.org/convert-string-to-float-in-python/)

Python 定义了类型转换函数，直接将一种数据类型转换成另一种数据类型。本文旨在提供关于将字符串转换为浮点的信息。在 Python 中，我们可以使用 [**float()**](https://www.geeksforgeeks.org/float-in-python/) 将 String 转换为 float。

### **Float()**

此函数用于将任何数据类型转换为浮点数。

**语法:**

```py
float(x)
```

该方法只接受一个参数，该参数也是可选的。如果没有传递参数，则该方法返回 0.0。

**例 1:**

## 蟒 3

```py
string= "3.141"

print(string)
print(type(string))

# converting string to float
Float = float(string)  

print(Float)
print(type(Float))
```

**输出:**

```py
3.141
<type 'str'>
3.141
<type 'float'>
```

**例 2:**

## 蟒 3

```py
string = '55.567'

float = float(string)

print(type(float))
print('Float Value =', float)
```

**输出:**

```py
<type 'float'>
('Float Value =', 55.567)
```