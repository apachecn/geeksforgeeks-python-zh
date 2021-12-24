# Python |逆快速沃尔什哈达玛变换

> 原文:[https://www . geesforgeks . org/python-reverse-fast-Walsh-hada mard-transformation/](https://www.geeksforgeeks.org/python-inverse-fast-walsh-hadamard-transformation/)

## **逆快速沃尔什哈达玛变换**

这是一种计算逆沃尔什哈达玛变换(WHT)的**哈达玛有序**高效算法。正常的 WHT 计算具有**N = 2<sup>m</sup>T5】的复杂性，但是使用 IFWHT 将计算减少到 **O(n <sup>2</sup> )** 。FWHT 需要 **O(n logn)** 的加减运算。这是一个分治算法，递归地分解 WHT。**

## **sympy . discrete . transforms . if wht():**

它可以执行**逆沃尔什哈达玛变换(WHT)** 。该方法基于哈达玛序列排序。序列会自动向右填充零，因为基数-2 FWHT 要求采样点数为 2 的幂。

```py

Syntax: 
sympy.discrete.transforms.ifwht()

Parameters : 
-> seq : [iterable] sequence on which IWHT is to be applied.

Returns : 
Coefficient of Inverse Fast Walsh Hadamard Transform Transform

```

**示例#1 :**

```py
# import sympy 
from sympy import ifwht

# sequence 
seq = [15, 21, 13, 44]

# ifwht
transform = ifwht(seq)
print ("Transform  : ", transform)
```

**输出:**

```py
Transform  :  [93/4, -37/4, -21/4, 25/4]
```

**例 2 :**

```py
# import sympy 
from sympy import ifwht

# sequence 
seq = [23, 
       56, 
       12, 
       555]

# ifwht
transform = ifwht(seq)
print ("Transform  : ", transform)
```

**输出:**

```py
Transform  :  [323/2, -144, -122, 255/2]

```