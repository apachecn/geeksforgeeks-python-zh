# Python 中如何取整数输入？

> 原文:[https://www . geesforgeks . org/如何在 python 中获取整数输入/](https://www.geeksforgeeks.org/how-to-take-integer-input-in-python/)

在这篇文章中，我们将看到如何在 Python 中接受整数输入。我们知道 Python 内置的 input()函数总是返回一个字符串类对象。因此，为了获取整数输入，我们必须使用 Python 内置的 [int()](https://www.geeksforgeeks.org/python-int-function/) 函数将这些输入类型转换为整数。

让我们看看例子:

**例 1:**

## 蟒蛇 3

```py
# take input from user
input_a = input()

# print data type
print(type(input_a))

# type cast into integer
input_a = int(input_a)

# print data type
print(type(input_a))
```

**输出:**

```py
100
<class 'str'>
<class 'int'>

```

**例 2:**

## 蟒蛇 3

```py
# string input
input_a = input()

# print type
print(type(input_a))

# integer input
input_b = int(input())

# print type
print(type(input_b))
```

**输出:**

```py
10
<class 'str'>
20
<class 'int'>

```

**例 3:**

## 蟒蛇 3

```py
# take multiple inputs in array
input_str_array = input().split()

print("array:", input_str_array)

# take multiple inputs in array
input_int_array = [ int(x) for x in input().split()]

print("array:", input_int_array)
```

**输出:**

```py
10 20 30 40 50 60 70
array: ['10', '20', '30', '40', '50', '60', '70']
10 20 30 40 50 60 70
array: [10, 20, 30, 40, 50, 60, 70]

```