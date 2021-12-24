# 在 Python 中为变量分配函数

> 原文:[https://www . geesforgeks . org/将函数赋值给 python 中的变量/](https://www.geeksforgeeks.org/assign-function-to-a-variable-in-python/)

在本文中，我们将看到如何在 Python 中将函数赋给变量。在 Python 中，我们可以给变量分配一个函数。使用这个变量，我们可以任意多次调用这个函数。从而提高代码的可重用性。

**实施**

只需将函数分配给所需的变量，但不使用()即可，即只使用函数的名称。如果变量与函数一起用括号()赋值，则不会返回任何值。

**语法**:

```
def func():
{
..
}

var=func

var()
var()
```

**示例:**

## 蟒蛇 3

```
def a():
  print("GFG")

# assigning function to a variable
var=a

# calling the variable
var()
```

**输出:**

```
GFG
```

以下程序将帮助您更好地理解:

**例 1:**

## 蟒蛇 3

```
# defined function
x = 123

def sum():
    x = 98
    print(x)
    print(globals()['x'])

# drivercode
print(x)

# assigning function
z = sum

# invoke function
z()
z()
```

**输出:**

```
123
98
123
98
123
```

**示例 2:** 参数化函数

## 蟒蛇 3

```
# function defined
def even_num(a):
    if a % 2 == 0:
        print("even number")
    else:
        print("odd number")

# drivercode
# assigning function
z = even_num

# invoke function with argument
z(67)
z(10)
z(7)
```

**输出:**

```
odd number
even number
odd number
```

**例 3:**

## 蟒蛇 3

```
# function defined
def multiply_num(a):
    b = 40
    r = a*b
    return r

# drivercode
# assigning function
z = multiply_num

# invoke function
print(z(6))
print(z(10))
print(z(100))
```

**输出:**

```
240
400
4000
```