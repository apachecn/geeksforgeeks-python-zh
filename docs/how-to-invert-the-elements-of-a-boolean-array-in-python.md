# 如何在 Python 中反转布尔数组的元素？

> 原文:[https://www . geeksforgeeks . org/如何反转 python 中布尔数组的元素/](https://www.geeksforgeeks.org/how-to-invert-the-elements-of-a-boolean-array-in-python/)

给定一个布尔数组，这里的任务是反转它的元素。布尔数组是只包含布尔值如真或假、1 或 0 的数组。

> **输入:** A=【真、真、假】
> 
> **输出:** A=【假，假，真】
> 
> **输入:** A=[0，1，0，1]
> 
> **输出:** A=[1，0，1，0]

**方法 1:**

您可以使用简单的 if else 方法来反转数组。在下面显示的实现方法中，您只需要检查数组中每个索引的值，如果值为真，将其更改为假，否则将其更改为真。这是反转布尔数组元素的最简单方法之一。

**程序:**

## 蟒蛇 3

```
a1 = ((0, 1, 0, 1))
a = list(a1)

for x in range(len(a)):
    if(a[x]):
        a[x] = 0
    else:
        a[x] = 1

print(a)
```

**输出:**

```
[1, 0, 1, 0]
```

**方法二:**

您也可以使用 numpy 库的内置函数来反转整个数组。

**语法:**

```
np.invert(boolean[] a)
```

**程序:**

## 计算机编程语言

```
import numpy as np

a = np.array((True, True, False, True, False))
b = np.invert(a)
print(b)
```

**输出:**

```
[False False  True False  True]
```

**方法 3:**

我们还可以在计算中使用 **Tilde 运算符** ( **~** )也称为按位求反运算符来求给定数组的反。它将数字 n 作为二进制数，并将所有 0 位“翻转”为 1，将 1 翻转为 0，从而获得补码二进制数。

所以在布尔数组中对于**为真或 1** 会得到 **-2** ，对于**为假或 0** 会得到 **-1。**再次使用 if..否则我们可以将数组转换成或所需的答案。

**程序:**

## 蟒蛇 3

```
a1 = ((0, 1, 0, 1))
a = list(a1)

for x in range(len(a)):
    # using Tilde operator(~)
    a[x] = ~a[x]

print(a)
```

**输出:**

```
[-1, -2, -1, -2]
```