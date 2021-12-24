# Python 中列表理解和 Lambda 的区别

> 原文:[https://www . geesforgeks . org/列表理解和 python 中 lambda 的区别/](https://www.geeksforgeeks.org/difference-between-list-comprehension-and-lambda-in-python/)

[**列表理解:**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) 列表理解是 python 中定义和创建列表的优雅方式。我们可以创建列表，就像数学陈述一样，并且只在一行中。列表理解的语法更容易掌握。列表理解通常包括以下几个部分:

*   输出表达式，
*   输入序列，
*   一个表示输入序列成员的变量，并且
*   可选谓词部分。

```py
List = [expression(i) for i in another_list if filter(i)]

```

**示例:**

```py
lst  =  [x ** 2  for x in range (1, 11)   if  x % 2 == 1]
print(lst)
```

**输出:**

```py
[1, 9, 25, 49, 81]
```

在上面的例子中，

*   x ** 2 是表达式。
*   范围(1，11)是输入序列或另一个列表。
*   x 是变量。
*   如果 x % 2 == 1 是谓词部分。

[**【Lambda:**](https://www.geeksforgeeks.org/python-lambda/)在 Python 中，匿名函数意味着函数没有名字。正如我们已经知道的，def 关键字用于定义普通函数，lambda 关键字用于创建匿名函数。它具有以下语法:

**语法:**

```py
lambda arguments : expression
```

**示例:**

```py
lst = list(map(lambda x: x**2, range(1, 5)))
print(lst)
```

**输出:**

```py
[1, 4, 9, 16]
```

## Lambdas 与列表理解的区别

列表理解用于创建列表，Lambdas 是可以像其他函数一样处理的函数，因此可以返回值或列表。
**例:**

```py
# list from range 0 to 10
list_ = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(list_)

# lambda function
lambda_list = list(map(lambda x: x * 2, list_))

# Map basically iterates every element
# in the list_ and returns the lambda 
# function result
print(lambda_list)

# list comprehension
list_comp = [x * 2 for x in list_]
print(list_comp)
```

**输出:**

```py
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```