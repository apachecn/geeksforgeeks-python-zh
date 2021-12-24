# Python 中的模幂运算

> 原文:[https://www . geesforgeks . org/modular-indexing-python/](https://www.geeksforgeeks.org/modular-exponentiation-python/)

给定三个数字 x，y 和 p，计算(x^y)p %

示例:

```
Input:  x = 2, y = 3, p = 5
Output: 3
Explanation: 2^3 % 5 = 8 % 5 = 3.

Input:  x = 2, y = 5, p = 13
Output: 6
Explanation: 2^5 % 13 = 32 % 13 = 6.

```

上述解决方案的问题是，对于大的 n 或 x 值，可能会发生溢出。因此，功率通常在大数模下评估。

天真乘法是 O(n)，常数因子很低，有%m.
[Pow](https://www.geeksforgeeks.org/pow-in-python/) 函数在 python 中用 O(log n)时间计算，但是当数字足够大时，如果首先计算 x <sup>y</sup> 的值，然后用 p 对其进行 mod，得到(x <sup>y</sup> ) % p 的求值结果，会花费很多时间。

```
# Simple python code that first calls pow() 
# then applies % operator.
a = 2
b = 100
p = (int)(1e9+7)

# pow function used with %
d = pow(a, b) % p
print (d)
```

**输出:**

```
976371285

```

在以大数为模进行计算时，运算符(%)花费大量时间，因此使用快速模幂运算。Python 有**次幂(x，e，m)** 来得到模的计算结果，这要少花很多时间。【详见 [Python 文档](https://docs.python.org/2/library/functions.html)

```
# Fast python code that first calls pow() 
# then applies % operator
a = 2
b = 100
p = (int)(1e9+7)

# Using direct fast method to compute 
# (a ^ b) % p.
d = pow(a, b, p)
print (d)
```

**输出:**

```
976371285

```

快速模幂运算算法在[链接](https://www.geeksforgeeks.org/modular-exponentiation-power-in-modular-arithmetic/)中有更简要的解释