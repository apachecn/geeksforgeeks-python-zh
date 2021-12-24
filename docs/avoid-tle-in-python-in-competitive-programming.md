# 在竞技编程中避免 Python 中的 TLE

> 原文:[https://www . geeksforgeeks . org/invite-tle-in-python-in-competitive-programming/](https://www.geeksforgeeks.org/avoid-tle-in-python-in-competitive-programming/)

**<u>获得 TLE 背后的原因</u> :**

*   It is slower than other programming languages.
*   It provides slower [input/output](https://www.geeksforgeeks.org/python-input-methods-competitive-programming/) .
*   Its recursion depth is low, which often gives TLE in [recursion](https://www.geeksforgeeks.org/recursion/) and [graph](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/) .

**<u>提示避免 TLE 搭配</u>** [**<u>蟒蛇</u>**](https://www.geeksforgeeks.org/python-programming-language/) **:**

### **<u>转换为迭代方法</u> :**

*   递归的任何问题都可以转化为迭代的方法，所以尽量用迭代的方法代替[递归](https://www.geeksforgeeks.org/recursion/)。
*   使用[栈](https://www.geeksforgeeks.org/stack-data-structure/)和[循环](https://www.geeksforgeeks.org/loops-in-c-and-cpp/)可以节省程序的执行时间。

**程序 1:**

下面给出的代码显示了两种方法中计算一个数的阶乘所需的时间:

## python 3

```py
# Program to show the time taken in
# iteration and recursion

import time

# Recursive function to find factorial
# of the given number N
def factorial(N):

      # Base Case
    if N == 0:
        return 1

    # Recursive Call
    return N * factorial(N - 1)

# Driver Code
if __name__ == '__main__':
    n = 20

    # Find the time taken for the
    # recursive approach
    start = time.perf_counter()
    print("Calculated using recursion: ", factorial(n))

    end = time.perf_counter()
    print("Time taken in recursion: ", "{0:.9f}".format(end-start))

    # Find time taken for iterative
    # approach
    start = time.perf_counter()
    result = 1

    while n > 0:
        result *= n
        n -= 1

    print("Calculated using the iterative method: ", result)

    end = time.perf_counter()
    print("Time taken in iteration: ", "{0:.9f}".format(end-start))
```

**输出:**

```py
Calculated using recursion:  2432902008176640000
Time taken in recursion:  0.000015925
Calculated using the iterative method:  2432902008176640000
Time taken in iteration:  0.000009279

```

### **<u>设置递归限制</u> :**

*   使用[**sys . setrecursionlimit()**](https://www.geeksforgeeks.org/python-sys-setrecursionlimit-method/)将 Python 解释器堆栈的最大深度设置为程序所需的整数值。
*   如果新的限制在当前递归深度太低，它将引发 [**递归错误异常**](https://www.geeksforgeeks.org/python-handling-recursion-limit/) 。

> **语法:** sys.setrecursionlimit(限制)
> 
> **参数:**限制:可以用来设置 Python 解释器堆栈限制的整数值。
> 
> **返回:**不返回任何内容。

**程序 2:**

下面是说明使用 **sys.setrecursionlimit()** 方法的程序:

## python 3

```py
# Python3 program to explain the 
# sys.setrecursionlimit() method

import sys

# Print the current recursion limit
# using sys.getrecursionlimit()
print("Original recursion limit was: ")
print(sys.getrecursionlimit())

# Set a new recursion limit
sys.setrecursionlimit(10**6)

# Print the new recursion limit
print("New recursion limit is: ")
print(sys.getrecursionlimit())
```

**输出:**

```py
Original recursion limit was: 
1000
New recursion limit is: 
1000000

```