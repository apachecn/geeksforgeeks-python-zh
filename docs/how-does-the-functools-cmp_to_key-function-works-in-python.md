# func tools CMP _ to _ key 函数在 Python 中是如何工作的？

> 原文:[https://www . geesforgeks . org/func tools-CMP _ to _ key-func-works-in-python/](https://www.geeksforgeeks.org/how-does-the-functools-cmp_to_key-function-works-in-python/)

Python 的 [sorted()](https://www.geeksforgeeks.org/sorted-function-python/) 函数发生了变化，它现在接受三个值，即 iterable、key 和 reverse。其中最后两个是可选的，但本文强调了[排序的关键部分()](https://www.geeksforgeeks.org/sorted-function-python/)功能。关键是，它有助于排序时可迭代元素的比较。Python 已经有了 cmp()函数，用于比较两个值并返回 1、-1 或 0。但是从 Python 3.0 及更高版本开始，这个函数已经被弃用，并且引入了一个新的函数 cmp_to_key()。下面的文章讨论了这个函数的应用和解释。

### 定义

*   cmp_to_key()使用一个键来比较元素
*   它内置于 functools 模块中，因此必须首先导入 functools 才能使用该函数
*   与接受诸如 min()、max()、sorted()等关键函数的工具一起使用。
*   只接受一个严格来说应该是可调用的参数
*   这个函数返回一个特殊的键，可以用来比较元素

**语法:**

> functools.cmp_to_key(可调用)

### 说明

*   将每个元素与列表中的每个其他元素进行比较，直到得到一个排序列表
*   显然，每个元素都用列表的另一个元素调用 mycmp()函数
*   函数的作用是:在比较数字后返回一个键
*   这个键最终帮助 sorted()以升序排列元素

下面是实现。

**示例 1:** 使用 cmp_to_key()函数提供的键对列表进行排序的程序

## 蟒蛇 3

```py
import functools

def mycmp(a, b):
    print("comparing ", a, " and ", b)
    if a > b:
        return 1
    elif a < b:
        return -1
    else:
        return 0

print(sorted([1, 2, 4, 2], key=functools.cmp_to_key(mycmp)))
```

**输出:**

```py
comparing  2  and  1
comparing  4  and  2
comparing  2  and  4
comparing  2  and  2
comparing  2  and  4
[1, 2, 2, 4]

```

**示例 2:** 使用 cmp_to_key()函数提供的键从列表中打印最大值和最小值的程序

## 蟒蛇 3

```py
import functools

def mycmp(a, b):
    print("comparing ", a, " and ", b)
    if a > b:
        return 1
    elif a < b:
        return -1
    else:
        return 0

print(min([45, 78, 813], key=functools.cmp_to_key(mycmp)))
print(max([45, 78, 813], key=functools.cmp_to_key(mycmp)))
```

**输出:**

```py
comparing  78  and  45
comparing  813  and  45
45
comparing  78  and  45
comparing  813  and  78
813

```