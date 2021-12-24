# Python def 关键字

> 原文:[https://www.geeksforgeeks.org/python-def-keyword/](https://www.geeksforgeeks.org/python-def-keyword/)

**Python def 关键字**用于定义函数，它放在用户提供的函数名之前，用于创建用户定义的函数。在 python 中，函数是一个逻辑代码单元，包含一系列使用“ **def** 关键字给定的名字下缩进的语句。在 python 中，def 关键字是最常用的关键字。

**语法:**

```
def function_name: 
    function definition statements...
```

**使用 def 关键字:**

*   对于类，def 关键字用于定义类的方法。
*   还需要 def 关键字来定义类的特殊成员函数，如 __init__()。

可能的实际应用是，它提供了代码可重用的特性，而不是一次又一次地编写代码，我们可以定义一个函数，并借助 **def** 关键字在函数内部编写代码。在下面给出的示例中将会更加清楚。根据用例的不同，def 可能有很多应用。

**例 1:**def 关键字的使用。

在这个例子中，我们将使用 def 关键字创建一个用户定义函数。

## 蟒蛇 3

```
# Python3 code to demonstrate
# def keyword

# function for subtraction of 2 numbers.
def subNumbers(x, y):
    return (x-y)

# main code
a = 90
b = 50

# finding subtraction
result = subNumbers(a, b)

# print statement
print("subtraction of ", a, " and ", b, " is = ", result)
```

**输出:**

```
subtraction of  90  and  50  is =  40
```

**例 2:** 用户定义一个前 10 个质数的函数。

## 蟒蛇 3

```
# Python program to print first 10
# prime numbers

# A function name prime is defined
# using def
def prime(n):
    x = 1
    count = 0
    while count < n:
        for d in range(2, x, 1):
            if x % d == 0:
                x += 1
        else:
            print(x)
            x += 1
            count += 1

# Driver Code
n = 10

# print statement
print("First 10 prime numbers are:  ")
prime(n)
```

**输出:**

```
First 10 prime numbers are:  
1
2
3
5
7
11
13
17
19
23
```

**示例 3:** 用户定义一个带有阶乘数的函数。

## 蟒蛇 3

```
# Python program to find the
# factorial of a number

# Function name factorial is defined
def factorial(n):
    if n == 1:
        return n
    else:
        return n*factorial(n-1)

# Main code
num = 6

# check is the number is negative
if num < 0:
    print("Sorry, factorial does not exist for negative numbers")
elif num == 0:
    print("The factorial of 0 is 1")
else:
    print("The factorial of", num, "is", factorial(num))
```

**输出:**

```
The factorial of 6 is 720
```