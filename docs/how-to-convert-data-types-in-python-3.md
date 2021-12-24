# 如何在 Python 3 中转换数据类型？

> 原文:[https://www . geeksforgeeks . org/如何转换 python 中的数据类型-3/](https://www.geeksforgeeks.org/how-to-convert-data-types-in-python-3/)

**先决条件:** [Python 数据类型](https://www.geeksforgeeks.org/python-data-types/)

类型转换是将一种数据类型转换为另一种数据类型的过程。Python 中可以有两种类型的类型转换–

*   隐式类型转换
*   显式类型转换

## 隐式类型转换

这是一种类型转换，其中句柄自动将一种数据类型转换为另一种数据类型，而无需用户参与。

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate
# implicit type conversion

# Python automatically converts
# a to int
a = 5
print(type(a))

# Python automatically converts
# b to float
b = 1.0
print(type(b))

# Python automatically converts
# c to int as it is a floor division
c = a//b
print(c)
print(type(c))
```

**输出:**

```
<class 'int'>
<class 'float'>
5.0
<class 'float'>
```

在上面的例子中，可以看到 Python 自动处理所有的类型转换，没有任何用户参与。

## 显式类型转换

在显式类型转换中，需要用户参与。用户根据自己的需要将一种数据类型转换成另一种。这可以借助 [str()](https://www.geeksforgeeks.org/python-str-function/) 、 [int()](https://www.geeksforgeeks.org/python-int-function/) 、 [float()](https://www.geeksforgeeks.org/float-in-python/) 等来完成。功能。让我们看看各种类型转换的处理。

### 带字符串的类型转换

一个[字符串](https://www.geeksforgeeks.org/python-strings/)一般是一个或多个字符的序列。我们经常需要将字符串转换成数字，反之亦然。让我们详细看看每一个。

#### 将数字转换为字符串

可以使用 [str()](https://www.geeksforgeeks.org/python-str-function/) 函数将一个数字转换为字符串。为此，请将包含数值的数字或变量传递给此函数。

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate
# type conversion of number to
# string

a = 10

# Converting number to string
s = str(a)
print(s)
print(type(s))
```

**输出:**

```
10
<class 'str'>
```

当我们想要向控制台打印一些包含数字的字符串时，这可能很有用。考虑下面的例子。

**示例:**

## 蟒蛇 3

```
s = "GFG"
n = 50

print("String: " + s + "\nNumber: " + str(n))
```

**输出:**

```
String: GFG
Number: 50
```

#### 将字符串转换为数字

可以使用 [int()](https://www.geeksforgeeks.org/python-int-function/) 或 [float()](https://www.geeksforgeeks.org/float-in-python/) 方法将字符串转换为数字。为此，将包含数值的有效字符串传递给这些函数中的任何一个(取决于需要)。

**注意:**如果传递了一个不包含数值的字符串，那么就会产生一个错误。

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate
# type conversion of string to
# number

s = '50'

# Converting to int
n = int(s)
print(n)
print(type(n))

# Converting to float
f = float(s)
print(f)
print(type(f))
```

**输出:**

```
50
<class 'int'>
50.0
<class 'float'>
```

### 带数字的类型转换

Python 中基本上有两种类型的数字——整数和浮点数。我们经常需要从一种类型转换到另一种类型。让我们详细看看他们的转换。

### 浮点到整数

可以使用 [int()](https://www.geeksforgeeks.org/python-int-function/) 函数将浮点转换为整数。为此，在 int()方法中传递一个浮点。

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate
# floating point to integer

f = 10.0

# Converting to integer
n = int(f)
print(n)
print(type(n))
```

**输出:**

```
10
<class 'int'>
```

### 整数到浮点

可以使用 [float()](https://www.geeksforgeeks.org/float-in-python/) 方法将整数转换为浮点数。为此，请在 float()方法中传递一个整数。

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate
# integer to float

n = 10

# Converting to float
f = float(n)
print(f)
print(type(f))
```

**输出:**

```
10.0
<class 'float'>
```

### 元组和列表之间的类型转换

在 Python 中，元组和列表都可以相互转换。可以使用[元组()](https://www.geeksforgeeks.org/tuples-in-python/)和[列表()](https://www.geeksforgeeks.org/python-list/)方法完成。为了更好的理解，请看下面的例子。

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate
# type conversion between list
# and tuples

t = (1, 2, 3, 4)
l = [5, 6, 7, 8]

# Converting to tuple
T = tuple(l)
print(T)
print(type(T))

# Converting to list
L = list(t)
print(L)
print(type(L))
```

**输出:**

```
(5, 6, 7, 8)
<class 'tuple'>
[1, 2, 3, 4]
<class 'list'>
```