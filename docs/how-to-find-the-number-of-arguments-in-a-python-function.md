# 如何求一个 Python 函数中的参数个数？

> 原文:[https://www . geeksforgeeks . org/如何找到 python 函数中的参数数量/](https://www.geeksforgeeks.org/how-to-find-the-number-of-arguments-in-a-python-function/)

在本文中，我们将看到如何计算 Python 中函数的参数数量。我们将使用 python 函数定义中使用的名为 [*args](https://www.geeksforgeeks.org/args-kwargs-python/) 的特殊语法。语法*args 允许我们向函数传递可变数量的参数。我们将在*args 中使用 [len()函数](https://www.geeksforgeeks.org/python-string-length-len/)或方法，以便计算 python 中该函数的参数数量。
**例 1:**

## 蟒蛇 3

```
def no_of_argu(*args):

    # using len() method in args to count
    return(len(args))

a = 1
b = 3

# arguments passed
n = no_of_argu(1, 2, 4, a)

# result printed
print(" The number of arguments are: ", n)
```

**输出:**

```
The number of arguments passed are: 4
```

**例 2:**

## 蟒蛇 3

```
def no_of_argu(*args):

    # using len() method in args to count
    return(len(args))

print(no_of_argu(2, 5, 4))
print(no_of_argu(4, 5, 6, 5, 4, 4))
print(no_of_argu(3, 2, 32, 4, 4, 52, 1))
print(no_of_argu(1))
```

**输出:**

```
3
6
7
1
```