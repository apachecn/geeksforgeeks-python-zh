# Python 3 中竞争性编程的数学技巧

> 原文:[https://www . geeksforgeeks . org/数学-竞赛技巧-python 编程-3/](https://www.geeksforgeeks.org/mathematics-tricks-for-competitive-programming-in-python-3/)

下面是 Python 3.8 在竞争性编程中为程序员提供的一些令人兴奋的特性。这些新特性与一些竞争程序员经常使用的数学函数和算法有关。这些特性的实现具有时间复杂性，这在从头开始实现程序的情况下是相同的。
我们将讨论

*   模幂运算
*   乘法模逆
*   计算 n <sub>Cr</sub> 和 n <sub>Pr</sub>

#### 模幂运算

给定 3 个数字 A、B 和 Mod。计算(A <sup>B</sup> )%Mod。
**例:**

```py
Input : A = 4, B = 3 Mod = 11 
Output : 9 
Explanation: (43)%11 = (64)%11 = 9

Input : A = 3, B = 3 Mod = 5 
Output : 2
Explanation: (33)%5 = (27)%5 = 2
```

这里讨论了传统的模幂运算实现
下面是讨论的 Python3.8 解决方案

## 大蟒

```py
A = 4
B = 3
Mod = 11

# Power function can take 3
# parameters and can compute
# (A ^ B)% Mod
print(f'The power is {pow(A, B, Mod)}')
```

**输出:**

```py
The power is 9
```

#### 模乘逆

给定两个整数 A 和 Mod，在模 Mod 下计算 A 的模乘逆。
模乘逆是整数 B，使得

```py
(A.B)%Mod = 1 where gcd(A, Mod) should be equal to 1
```

**例:**

```py
Input : A = 4, Mod = 11  
Output : 3 
Explanation: (4*3)%11 = (12)%11 = 1

Input : A = 3, Mod = 5 
Output : 2
Explanation: (3*2)%5 = (6)%5 = 1
```

模块乘法逆的传统实现在这里讨论
下面是讨论的 Python3.8 解决方案

## 计算机编程语言

```py
A = 4
Mod = 11

# Power function can take 3 parameters
# and can compute (A^-1)% Mod
print(f'The Modular Multiplicative Inverse \
of A under Mod is {pow(A, -1, Mod)}')
```

**输出:**

```py
The Modular Multiplicative Inverse of A under Mod is 3
```

#### 计算 Ncr 和 Npr

给定 N 和 r 的值，计算 Ncr(一次取 r 的 N 个事物的组合)和 Npr(一次取 r 的 N 个事物的排列)。
**例:**

```py
Input : N = 10, r = 3  
Output : Ncr = 120

Input : N = 10, r = 3  
Output : Npr = 720
```

Ncr 和 Npr 的传统实现在这里和
讨论，下面是讨论的 Python3.8 解决方案。

## 大蟒

```py
import math
N = 10
r = 3

print(f"Ncr = {math.comb(N, r)}")
print(f"Npr = {math.perm(N, r)}")
```

**输出:**

```py
Ncr = 120
Npr = 720
```