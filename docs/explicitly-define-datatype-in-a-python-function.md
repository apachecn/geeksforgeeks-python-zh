# 在 Python 函数中明确定义数据类型

> 原文:[https://www . geesforgeks . org/显式定义-python 中的数据类型-函数/](https://www.geeksforgeeks.org/explicitly-define-datatype-in-a-python-function/)

不像其他语言 Java、C++等。Python 是一种强类型的动态语言，在这种语言中，我们不必指定函数返回值和函数参数的数据类型。它将类型与值而不是名称联系起来。指定特定类型数据的唯一方法是在调用函数时提供显式数据类型。

**例 1:** 我们有一个函数可以添加 2 个元素。

## 蟒蛇 3

```
# function definition
def add(num1, num2):
    print("Datatype of num1 is ", type(num1))
    print("Datatype of num2 is ", type(num2))
    return num1 + num2

# calling the function without
# explicitly declaring the datatypes
print(add(2, 3))

# calling the function by explicitly
# defining the datatype as float
print(add(float(2), float(3)))
```

**输出:**

```
Datatype of num1 is  <class 'int'>
Datatype of num2 is  <class 'int'>
5
Datatype of num1 is  <class 'float'>
Datatype of num2 is  <class 'float'>
5.0

```

**示例 2:** 我们有一个字符串连接的函数

## 蟒蛇 3

```
# function definition
def concatenate(num1, num2):
    print("Datatype of num1 is ", type(num1))
    print("Datatype of num2 is ", type(num2))
    return num1 + num2

# calling the function without
# explicitly declaring the datatypes
print(concatenate(111, 100))

# calling the function by explicitly
# defining the datatype as float
print(concatenate(str(111), str(100)))
```

**输出:**

```
Datatype of num1 is  <class 'int'>
Datatype of num2 is  <class 'int'>
211
Datatype of num1 is  <class 'str'>
Datatype of num2 is  <class 'str'>
111100

```