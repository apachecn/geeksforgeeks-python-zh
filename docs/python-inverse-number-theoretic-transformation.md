# Python |逆数论变换

> 原文:[https://www . geeksforgeeks . org/python-逆数论-变换/](https://www.geeksforgeeks.org/python-inverse-number-theoretic-transformation/)

逆数论变换是快速傅里叶变换定理的推广。它是通过用第 n 个原始单位根替换 **e^(-2piik/N)** 获得的。所以这意味着，代替复数 C，在商环上使用变换 **Z/pZ** 。该理论基于并使用了有限域和数论的概念。

逆数论变换模必须是素数。但是如果它是质数，它会让事情变得更简单。人们可以用复合模量来执行逆 NTT。对于模数:

*   n <sup>第</sup>根的统一存在
*   n 的乘法逆

数论变换基本上是**傅里叶变换**。此外，假设给出了一个标准的离散傅里叶变换，并且可以通过将数据乘以傅里叶矩阵以矩阵的形式完成。让我们假设 N = 4。然后，矩阵可以是–

```
[ 1   1    1    1  ]
[ 1   w   w^2  w^3 ]
[ 1  w^2  w^4  w^6 ]
[ 1  w^3  w^6  w^9 ]

```

## **sympy . discrete . transforms . intt():**

它可以对序列进行**逆数论变换(NTT)** 。它专门研究离散傅里叶变换商环，对于素数而不是复数，它使用 **Z/pZ** 。

由于基数为 2 的快速傅立叶变换要求样本点数为 2 的幂，因此序列会自动向右填充零。

```

Parameters : 
-> seq       : [iterable] sequence on which DFT is to be applied.
-> prime no. : [Integer] prime modulus for INTT to perform on.

Returns : 
Number Theoretic Transform

```

**示例#1 :**

```
# import sympy 
from sympy import intt

# sequence 
seq = [15, 21, 13, 44]

prime_no = 3 * 2**8 + 1

# intt
transform = intt(seq, prime_no)
print ("Inverse NTT : ", transform)
```

**输出:**

```
Inverse NTT :  [600, 357, 183, 413]
```

 **例 2 :**

```
# import sympy 
from sympy import intt

# sequence 
seq = [153, 321, 133, 44, ]

# Prime modulus of the form (m * 2**k + 1)
prime_no = 3 * 2**8 + 1

# intt
transform = intt(seq, prime_no)
print ("Inverse NTT : ", transform)
```

**输出:**

```
Inverse NTT :  [355, 710, 557, 69]

```