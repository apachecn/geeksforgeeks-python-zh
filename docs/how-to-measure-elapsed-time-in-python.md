# 如何在 Python 中测量经过时间？

> 原文:[https://www . geesforgeks . org/如何测量 python 中的运行时间/](https://www.geeksforgeeks.org/how-to-measure-elapsed-time-in-python/)

在 Python 中，我们有三个模块可以帮助我们找到程序的执行时间。我们将在本文中探讨其中的每一个，以及它可能帮助我们执行程序的一些功能。我们将使用的模块是**时间**、**时间**和**日期时间**。我们将在本文中找出经过的时间(程序执行所花费的时间)。

### 使用时间信息模块

Python **timeit** 模块常用来度量小代码片段的执行时间。我们还可以使用 timeit()函数，该函数执行一个匿名函数，并执行多次。在计算执行时间时，它会暂时关闭垃圾收集(收集无用变量的过程，这些变量的使用已经结束，并通过将它们标记为垃圾值来释放内存来清除它们)。

在第一个例子中，我们将分析如何使用 timeit 模块，并使用它来查找 lambda 表达式的执行时间。代码从导入时间模块开始，然后我们使用。timeit()模块，用于查找执行该功能所需的时间。最后，我们在屏幕上打印结果。

## 蟒蛇 3

```
# importing the module
import timeit

# using the timeit method and lambda 
# expression to get the execution time of
# the function.
t = timeit.timeit(lambda: "print('Hello World!')")

# printing the execution time
print(t)
```

**输出:**

```
0.0777151
```

现在我们将检查如何使用 **timeit.timeit()** 函数来获取函数的执行时间。该函数从导入模块开始，然后我们创建一个示例函数，我们希望计算它的执行时间。然后我们使用 **timeit.timeit()** 函数，调用函数内部的函数作为参数，下一个参数就是定义我们执行这个函数的次数的数字。然后我们在下一行打印经过的时间或执行时间。

## 蟒蛇 3

```
# importing the module
import timeit

# sample function that returns square
# of the value passed
def print_square(x):
    return (x**2)

# using the timeit method and lambda
# expression to get the execution time of
# the function, number defines how many
# times we execute this function
t = timeit.timeit(lambda: print_square(3), number=10)

# printing the execution time
print(t)
```

**输出:**

```
5.299999999999749e-06
```

现在，实际上为了估计程序的执行时间，我们通常不使用一次获得的值作为最终的正确值，因为程序的执行可能取决于特定时刻的操作系统和硬件的可用性。因此，通常我们采用多个执行时间值，通常计算出的平均值会给出最佳答案。为此，我们将使用 timeit.repeat()方法，而不是 timeit.timeit()方法，该方法接受一个 repeat 参数，省去了创建循环并将值存储在数组中的麻烦。

## 蟒蛇 3

```
# importing the module
import timeit

# sample function that returns square
# of the value passed
def print_square(x):
    return (x**2)

# using the repeat method and lambda
# expression to get the execution time of
# the function, number defines how many
# times we execute this function and the
# repeat defines the number of times the
# time calculation needs to be done.
t = timeit.repeat(lambda: print_square(3), number=10, repeat=5)

# printing the execution time
print(t)
```

**输出:**

> [5.800000000000249e-06，3.2999999997749 e-06，3.2000000000018125e-06，3.19999948736 e-06，
> 
> 3.40000000000006247 e-06]

此外，我们可以使用 timeit.default_timer()，它基本上记录了调用方法的瞬间的时间。所以我们在我们想要计算执行时间的代码行的前后调用方法，然后基本上这两个时间之间的差值给我们结果。为了找到时间，我们使用 timeit.defaultTimer()方法记录时间，然后在最后一行打印两个时间之间的差值。

## 蟒蛇 3

```
# importing the module
import timeit

# sample function that returns 
# square of the value passed
def print_square(x):
    return (x**2)

# records the time at this instant
# of the program
start = timeit.default_timer()

# calls the function
print_square(3)

# records the time at this instant 
# of the program
end = timeit.default_timer()

# printing the execution time by subtracting
# the time before the function from
# the time after the function
print(end-start)
```

**输出:**

```
2.299999999996749e-06
```

### 使用时间模块

我们可以像上面讨论的 timeit.default_timer()方法一样使用 time.perf_counter()方法。它可以使用最高分辨率的时钟，给你最准确的结果。事实上，timeit.default_timer()也使用 time.perf_counter()作为它的基。这也记录了需要计算其执行或运行时间的所需代码行前后的时间。然后我们从代码行之后的记录时间中减去行开始之前的记录时间。

## 蟒蛇 3

```
# importing the module
import time

# sample function that returns square
# of the value passed
def print_square(x):
    return (x**2)

# records the time at this instant of the 
# program
start = time.perf_counter()

# calls the function
print_square(3)

# records the time at this instant of the
# program
end = time.perf_counter()

# printing the execution time by subtracting
# the time before the function from
# the time after the function
print(end-start)
```

**输出:**

```
2.299999999996749e-06
```

要以纳秒为单位测量一段代码的运行时间或执行时间，我们可以使用 time.time_ns()函数。这遵循与 time.perf_counter()函数相同的语法，例如记录代码行前后的时间，然后减去这些值，然后将它们打印到屏幕上，但是它是以纳秒而不是秒来记录的。

## 蟒蛇 3

```
# importing the module
import time

# sample function that returns square 
# of the value passed
def print_square(x):
    return (x**2)

# records the time in nanoseceonds at
# this instant of the program
start = time.time_ns()

# calls the function
print_square(3)

# records the time in nanoseceonds at this
# instant of the program
end = time.time_ns()

# printing the execution time by subtracting 
# the time before the function from
# the time after the function
print(end-start)
```

**输出:**

```
0
```

> **注意:**由于我的电脑有相当好的处理器和 ram，在我的情况下用了 0 纳秒。但这取决于您的系统执行函数代码需要多少时间。

### 使用日期时间模块

[**【Datetime】**](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)模块也可用于查找代码块中经过或花费的时间，前提是您不需要高精度。datetime.now()的工作方式也与 timeit.default_timer()或 time.perf_counter()相同，但缺少与它们相同的精度。它以 HH:MM:SS 格式返回结果。该函数通常用于获取当前时间，而不是计算执行时间的首选用例。然而，这些程序可能需要相当长的时间来执行，比如训练 ML/AI 模型、网页抓取大型网站等。

## 蟒蛇 3

```
# importing the module
from datetime import datetime

# sample function that returns square 
# of the value passed
def print_square(x):
    return (x**2)

# records the time at this instant of
# the program in HH:MM:SS format
start = datetime.now()

# calls the function
print_square(3)

# records the time at this instant of the
# program in HH:MM:SS format
end = datetime.now()

# printing the execution time by subtracting
# the time before the function from
# the time after the function
print(end-start)
```

**输出:**

```
0:00:00
```