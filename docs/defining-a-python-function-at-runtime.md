# 在运行时定义 Python 函数

> 原文:[https://www . geesforgeks . org/defining-a-python-function-at-runtime/](https://www.geeksforgeeks.org/defining-a-python-function-at-runtime/)

在 python 中，我们可以定义一个 Python 函数，在运行时借助 **FunctionType()** 执行。首先我们导入**类型**模块，然后执行**编译()**函数并传递参数 exec，然后在运行时借助 FunctionType()定义函数。

**示例 1:** 打印 GEEKSFORGEEKS 的功能。

## 蟒蛇 3

```py
# importing the module
from types import FunctionType

# functttion during run-time
f_code = compile('def gfg(): return "GEEKSFORGEEKS"', "<string>", "exec")
f_func = FunctionType(f_code.co_consts[0], globals(), "gfg")

# calling the function
print(f_func())
```

**输出:**

```py
GEEKSFORGEEKS

```

**例 2:** 函数加 2 个数。

## 蟒蛇 3

```py
# importing the module
from types import FunctionType

# function at run-time
f_code = compile('def gfg(a, b): return(a + b) ', "<int>", "exec")
f_func = FunctionType(f_code.co_consts[0], globals(), "gfg")

val1 = 3999
val2 =4999

# calliong the function
print(f_func(val1, val2))
```

**输出:**

```py
8998
```