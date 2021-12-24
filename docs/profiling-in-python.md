# Python 中的剖析

> 原文:[https://www.geeksforgeeks.org/profiling-in-python/](https://www.geeksforgeeks.org/profiling-in-python/)

Python 提供了许多优秀的模块来衡量程序的统计数据。这让我们知道程序在哪里花费了太多的时间，以及如何优化它。为了提高程序的效率，最好优化代码。因此，执行一些标准测试以确保优化，我们可以改进程序以提高效率。

**使用定时器:**
定时器很容易实现，它们可以在程序的任何地方用来测量执行时间。通过使用计时器，我们可以得到准确的时间，我们可以改进程序中耗时过长的地方。`Time` 模块提供分析程序的方法。

**示例#1:**

```py
# importing time module
import time

start = time.time()
print("Time Consumed")
print("% s seconds" % (time.time() - start))
```

**Output:**

```py
Time Consumed
0.01517796516418457 seconds

```

**例 2:**

```py
# importing time module
import time

def gfg():
    start = time.time()
    print("Time consumed")
    end = time.time()
    print("gfg() function takes", end-start, "seconds")

# Calling gfg
gfg()
```

**Output:**

```py
Time consumed
gfg() function takes 0.015180110931396484 seconds

```

**使用 line_profiler:**
Python 提供了一个内置的模块来测量执行时间，模块名为 LineProfiler。它给出了一个程序消耗时间的详细报告。

**示例:**

```py
# importing line_profiler module
from line_profiler import LineProfiler

def geek(rk):
    print(rk)

rk ="geeks"
profile = LineProfiler(geek(rk))
profile.print_stats()
```

**Output:**

```py
Timer unit: 4.27198e-10 s

```

**使用 cProfile:**
Python 包含一个名为 cProfile 的内置模块，用于测量程序的执行时间，cProfiler 模块提供程序执行多长时间以及函数在程序中被调用多少次的所有信息。

**代码#1**

```py
# importing cProfile
import cProfile

cProfile.run("10 + 10")
```

**Output:**

```py
3 function calls in 0.000 seconds

   Ordered by: standard name

   ncalls  tottime  percall  cumtime  percall filename:lineno(function)
        1    0.000    0.000    0.000    0.000 :1()
        1    0.000    0.000    0.000    0.000 {built-in method builtins.exec}
        1    0.000    0.000    0.000    0.000 {method 'disable' of '_lsprof.Profiler' objects}

```

**代码#2:** 测量任何函数统计的 cProfile。

```py
# importing cProfile
import cProfile

def f():
    print("hello")
cProfile.run('f()')
```

**Output:**

```py
hello
         5 function calls in 0.000 seconds

   Ordered by: standard name

   ncalls  tottime  percall  cumtime  percall filename:lineno(function)
        1    0.000    0.000    0.000    0.000 3233da5f950795af777f4b63136f7efd.py:5(f)
        1    0.000    0.000    0.000    0.000 :1()
        1    0.000    0.000    0.000    0.000 {built-in method builtins.exec}
        1    0.000    0.000    0.000    0.000 {built-in method builtins.print}
        1    0.000    0.000    0.000    0.000 {method 'disable' of '_lsprof.Profiler' objects}

```