# 通过在 Python 中赋予二进制值来创建整型变量

> 原文:[https://www . geesforgeks . org/通过在 python 中赋值来创建整数变量/](https://www.geeksforgeeks.org/create-integer-variable-by-assigning-binary-value-in-python/)

给定一个二进制值，我们的任务是创建整数变量并以二进制格式赋值。要以二进制格式给变量赋值，我们使用 0b 后缀。它告诉编译器该值(以 0b 为后缀)是一个二进制值，并将其赋给变量。

```
Input: Var = 0b1010
Output: 10

Input: Var = 0b11001
Output: 25
```

注意:要打印二进制格式的值，我们使用 **bin()函数。**

**示例 1:** 二进制和十进制格式的简单演示

## 蟒蛇 3

```
num = 10

# print num in decimal and binary format 
print ("num (decimal) : ", num)
print ("num (binary ) : ", bin (num))
```

**输出:**

```
num (decimal) :  10
num (binary ) :  0b1010
```

**示例 2:** 通过指定二进制值的整数变量。

## 蟒 3

```
# Python code to create variable 
# by assigning binary value
a = 0b1010
b = 0b11001

#printing the values in decimal form
print("Value of a is: ", a)
print("Value of b is: ", b)

#printing the values again in binary form
print("Value of a in binary form", bin(a))
print("Value of b in binary form", bin(b))
```

**输出:**

```
Value of a is:  10
Value of b is:  25
Value of a in binary form 0b1010
Value of b in binary form 0b11001
```

如上所述，我们使用 0b 后缀。，它告诉编译器该值(以 0b 为后缀)是一个二进制值，并将其赋给变量。所以使用 bin()函数打印二进制形式也是打印的，它只是告诉所表示的数字是二进制形式。如果我们用十六进制形式而不是**“0b”“0x”**来打印这些数字，就会打印出来，用来告诉这个数字是用十六进制形式来表示的。