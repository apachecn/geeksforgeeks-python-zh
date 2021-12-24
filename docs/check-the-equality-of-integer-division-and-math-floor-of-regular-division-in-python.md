# 检查 Python 中整数除法和正则除法的 math.floor()是否相等

> 原文:[https://www . geeksforgeeks . org/检查 python 中整数除法和数学二进制除法的等式/](https://www.geeksforgeeks.org/check-the-equality-of-integer-division-and-math-floor-of-regular-division-in-python/)

对于大商来说，`floor division (//)`似乎不一定等于正规除法`(math.floor(a/b))`的下限

**例:**

```
Input : 269792703866060742 // 3 
Output : 89930901288686914

Input : math.floor(269792703866060742 / 3)
Output : 89930901288686912

```

在上面的例子中，`floor division(//)`的输出是 89930901288686914，数学. floor 的输出是 89930901288686912。除了本例中的最后两位数字，即 14 和 12 之外，所有数字都相等。

示例中商不相等的原因是，在`math.floor(a/b)`的情况下，结果是用浮点运算 **(IEEE-754 64 位)**计算的，这意味着存在最大精度。获得的商大于`2^53`极限，超过该极限浮点不再精确到单位。然而，`floor division(//)` Python 使用其无限的整数范围，因此结果是正确的。

**注意:**对于 int 和 long 参数，真除法(/)可能会丢失信息；这是真正分裂的本质(只要语言中没有推理)。有意识地使用 long 的算法应该考虑使用//，因为 long 的真正除法(/)保留的精度不超过 53 位(在大多数平台上)。

在典型的计算机系统中，“双精度”(64 位)二进制浮点数的系数为 53 位，指数为 11 位，符号位为 1 位。参考 [**IEEE 754**](https://en.wikipedia.org/wiki/IEEE_754) 。

**例:**

```
# Python program to demonstrate
# equality of integer division and 
# math.floor

import math

# First case: Take x smaller
# than 2 ^ 53 . 
x = 269
y = 3
if (x // y) == math.floor(x / y):
    print("Equal Output")

else:
    print("Not Equal Output")

# Second case: Take x larger
# than 2 ^ 53.
x = 269792703866060742
y = 3 
if (x // y) == math.floor(x / y):
    print("Equal Output")

else:
    print("Not Equal Output")
```

**输出:**

```
Equal Output
Not Equal Output

```