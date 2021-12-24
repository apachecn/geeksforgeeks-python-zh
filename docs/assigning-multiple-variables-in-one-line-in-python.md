# 在 Python 中一行指定多个变量

> 原文:[https://www . geeksforgeeks . org/python 一行多变量赋值/](https://www.geeksforgeeks.org/assigning-multiple-variables-in-one-line-in-python/)

变量是一个命名的内存空间，用于存储一些数据，这些数据又将用于一些处理。所有的编程语言都有一些变量声明机制，但是有一点是通用的，那就是名字和分配给它的数据。它们能够存储数据类型的值。

赋值运算符(=)将右边提供的值赋给左边给出的变量名。给出了变量声明的基本语法:

**语法:**

```py
var_name = value
```

**示例:**

```py
a = 4
```

## 在一行中分配多个变量

上面给出的是 Python 中只分配变量的机制，但是可以同时分配多个变量。Python 从右向左赋值。在单行中赋值多个变量时，赋值运算符左侧会提供不同的变量名，用逗号分隔。它们各自的值也是如此，只是它们应该在赋值运算符的右边。

以这种方式声明变量时，必须注意名称及其对应值的顺序赋值运算符左边的第一个变量名被赋值为右边的第一个值，以此类推。

**例 1:**

## 蟒蛇 3

```py
a, b = 4, 8
print("value assigned to a")
print(a)
print("value assigned to b")
print(b)
```

**输出:**

```py
value assigned to a
4
value assigned to b
8
```

单行中的变量赋值也可以针对不同的数据类型进行。

**例 2:**

## 蟒蛇 3

```py
print("assigning values of different datatypes")
a, b, c, d = 4, "geeks", 3.14, True
print(a)
print(b)
print(c)
print(d)
```

**输出:**

```py
assigning values of different datatypes
4
geeks
3.14
True
```

不仅仅是简单的变量赋值，赋值后执行一些操作也可以用同样的方式完成。

**例 3:**

## 蟒蛇 3

```py
a, b = 8, 3
add, pro = (a+b), (a*b)
print(add)
print(pro)
```

**输出:**

```py
11
24
```

**例 4:**

## 蟒蛇 3

```py
string = "Geeks"
a, b, c = string[0], string[1:4], string[4]

print(a)
print(b)
print(c)
```

**输出:**

```py
G
eek
s
```