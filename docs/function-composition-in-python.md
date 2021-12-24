# Python 中的函数组合

> 原文:[https://www . geesforgeks . org/function-composition-in-python/](https://www.geeksforgeeks.org/function-composition-in-python/)

**先决条件:** [减少()](https://www.geeksforgeeks.org/reduce-in-python/)、[λ](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

函数组合是将两个或两个以上的函数组合起来，使一个函数的输出成为第二个函数的输入，以此类推。例如，假设有两个函数“F”和“G”，它们的组成可以表示为 F(G(x))，其中“x”是自变量，G(x)函数的输出将成为 F()函数的输入。

**示例:**

```
# Function to add 2 
# to a number
def add(x):
    return x + 2

# Function to multiply 
# 2 to a number
def multiply(x):
    return x * 2

# Printing the result of 
# composition of add and 
# multiply to add 2 to a number 
# and then multiply by 2
print("Adding 2 to 5 and multiplying the result with 2: ", 
      multiply(add(5)))
```

**输出:**

```
Adding 2 to 5 and multiplying the result with 2: 14

```

**解释**
首先在输入 5 上调用`add()` 功能。`add()`将输入加 2，输出为 7，作为输入给`multiply()`，后者将其乘以 2，输出为 14

**更好的实现构图的方式**

有一个更好的方法来实现函数的组合。我们可以创建一个特殊的函数，它可以组合任何两个函数。

```
# Function to combine two
# function which it accepts 
# as argument
def composite_function(f, g):
    return lambda x : f(g(x))

# Function to add 2
def add(x):
    return x + 2

# Function to multiply 2
def multiply(x):
    return x * 2

# Composite function returns
# a lambda function. Here add_multiply
# will store lambda x : multiply(add(x))
add_multiply = composite_function(multiply, add)

print("Adding 2 to 5 and multiplying the result with 2: ",
      add_multiply(5))
```

**输出:**

```
Adding 2 to 5 and multiplying the result with 2: 14

```

**组成 N 个数的函数**
我们可以通过修改上面的方法组成任意个数的函数。

```
# Function to combine two 
# function which it accepts
# as argument
def composite_function(f, g):

    return lambda x : f(g(x))

# Function to add 2
def add(x):
    return x + 2

# Function to multiply 2
def multiply(x):
    return x * 2

# Function to subtract 2
def subtract(x):
    return x - 1

# Composite function returns
# a lambda function. Here
# add_subtract_multiply will 
# store lambda x : multiply(subtract(add(x)))
add_subtract_multiply = composite_function(composite_function(multiply,
                                                              subtract), 
                                           add)

print("Adding 2 to 5, then subtracting 1 and multiplying the result with 2: ",
      add_subtract_multiply(5))
```

**输出:**

> 将 2 加 5，然后减去 1，再将结果乘以 2: 12

现在我们将通过使用 functools 库中的 [reduce()](https://www.geeksforgeeks.org/reduce-in-python/) 函数，将我们的 composite_function 修改为一个可以组成任意数量函数的函数，而不是两个。

```
# importing reduce() from functools
from functools import reduce

# composite_function accepts N
# number of function as an 
# argument and then compose them
def composite_function(*func):

    def compose(f, g):
        return lambda x : f(g(x))

    return reduce(compose, func, lambda x : x)

# Function to add 2
def add(x):
    return x + 2

# Function to multiply 2
def multiply(x):
    return x * 2

# Function to subtract 2
def subtract(x):
    return x - 1

# Here add_subtract_multiply will 
# store lambda x : multiply(subtract(add(x))) 
add_subtract_multiply = composite_function(multiply,
                                           subtract,
                                           add)

print("Adding 2 to 5, then subtracting 1 and multiplying the result with 2: ", 
      add_subtract_multiply(5))
```

**输出:**

> 将 2 加 5，然后减去 1，再将结果乘以 2: 12

**解释**
`reduce()`函数是从*func 中取出前两个函数，使用`compose()`进行组合，然后将第三个函数组合到前面的组合函数中，以此类推。这里`multiply()`和`subtract()`先合成(乘(减(x))，再加()合成(乘(减(加(x))。