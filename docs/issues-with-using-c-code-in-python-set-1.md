# 在 Python 中使用 C 代码的问题|第 1 集

> 原文:[https://www . geesforgeks . org/issues-with-use-c-code-in-python-set-1/](https://www.geeksforgeeks.org/issues-with-using-c-code-in-python-set-1/)

**先决条件:**使用 Python 中的 C 代码| [集 1](https://www.geeksforgeeks.org/using-c-codes-in-python-set-1/) 、[集 2](https://www.geeksforgeeks.org/using-c-codes-in-python-set-2/)

**问题#1 :** 如果使用 *ctypes* ，那么就会出现一个问题，原来的 C 代码可能会使用没有干净利落地映射到 Python 的语言。

让我们以`[divide()](https://www.geeksforgeeks.org/using-c-codes-in-python-set-1/)`函数为例，它通过一个参数返回值。这是一种常见的 C 语言技术，但通常不清楚它在 Python 中应该如何工作。

```
divide = _mod.divide
divide.argtypes = (ctypes.c_int, ctypes.c_int, ctypes.POINTER(ctypes.c_int))
x = 0
divide(10, 3, x)
```

**输出:**

```
Traceback (most recent call last):
  File "", line 1, in 
ctypes.ArgumentError: argument 3: : expected LP_c_int
instance instead of int

```

**问题#2 :**
即使有效，那么也违反了 Python 对整数的不变性。对于涉及指针的参数，必须构造一个兼容的 *ctypes* 对象，并按照下面给定的代码进行传递。

```
x = ctypes.c_int()
print ("divide(10, 3, x) : ", divide(10, 3, x))

print ("x.value : ", x.value)
```

**输出:**

```
divide(10, 3, x) : 3

x.value : 1

```

**第三期:**

在下面的代码中，创建了一个 **ctypes.c_int** 的实例，并作为指针对象**传入。c_int** 对象可以变异，不像正常的 Python 整数。要检索或更改该值，**。值**属性即可使用。

```
# int divide(int, int, int *)
_divide = _mod.divide

_divide.argtypes = (ctypes.c_int, ctypes.c_int, ctypes.POINTER(ctypes.c_int))
_divide.restype = ctypes.c_int

def divide(x, y):
    rem = ctypes.c_int()
    quot = _divide(x, y, rem)
    return quot, rem.value
```

**第四期:**`avg()`功能是一个挑战。

底层的 C 代码需要一个表示数组的长度并接收一个指针。然而，从 Python 的角度来看，实际上，Python“数组”可以采取许多不同的形式，它可以是数组、列表、元组或 numpy 数组，并且您可能希望支持多种可能性。