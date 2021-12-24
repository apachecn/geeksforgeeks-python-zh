# Python 中的 PrimePy 模块

> 原文:[https://www.geeksforgeeks.org/primepy-module-in-python/](https://www.geeksforgeeks.org/primepy-module-in-python/)

质数是大于 1 的自然数，它的唯一因子是 1 和数本身。2 是唯一的偶数素数。我们可以用‘6n+1’或‘6n-1’(2 和 3 除外)来表示任何素数，其中 n 是自然数。

**primePy** 是 Python 的那个库，用来计算与素数相关的运算。借助这个 primePy 模块的功能，它将在更短的时间内完成所有功能。

## 安装库

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```py
 pip install primePy  
```

## 素数的函数

**1。primes.check(n)** :如果‘n’是素数，它将返回 True，否则它将返回 False。

**示例:**

## 蟒蛇 3

```py
# Importing primes function
# From primePy Library
from primePy import primes

print(primes.check(105))
print(primes.check(71))
```

**输出:**

```py
False
True
```

**2。primes.factor(n)** :它将返回“n”的最低质因数。

**示例:**

## 蟒蛇 3

```py
# Importing primes function
# From primePy Library
from primePy import primes

a = primes.factor(15)
print(a)

a = primes.factor(75689456252)
print(a)
```

**输出:**

```py
3
2
```

**3。primes.factors(n)** :如果存在的话，会返回所有带有重复因子的‘n’的 prime factors。

**示例:**

## 蟒蛇 3

```py
# Importing primes function
# From primePy Library
from primePy import primes

a = primes.factors(774177)
print(a)

a = primes.factors(15)
print(a)
```

**输出:**

```py
[3, 151, 1709]
[3, 5]
```

**4。primes.first(n)** :它将返回第一个‘n’个素数。

**示例:**

## 蟒蛇 3

```py
# Importing primes function
# From primePy Library
from primePy import primes

a = primes.first(5)
print(a)

a = primes.first(10)
print(a)
```

**输出:**

```py
[2, 3, 5, 7, 11]
[2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
```

**5。primes.upto(n)** :它将返回所有小于或等于' n '的素数。

**示例:**

## 蟒蛇 3

```py
# Importing primes function
# From primePy Library
from primePy import primes

a = primes.upto(17)
print(a)

a = primes.upto(100)
print(a)
```

**输出:**

> 【2、3、5、7、11、13、17】
> 【2、3、5、7、11、13、17、19、23、29、31、37、41、43、47、53、59、61、67、71、73、79、83、89、97】

**6。(m，n)之间的素数**:它将返回 m 和 n 之间的所有素数。

**示例:**

## 蟒蛇 3

```py
# Importing primes function
# From primePy Library
from primePy import primes

a = primes.between(4, 15)
print(a)

a = primes.between(25, 75)
print(a)
```

**输出:**

```py
[5, 7, 11, 13]
[29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73]
```

**7。素数φ(n)**:它将返回小于‘n’的整数个数，这些整数与 n 没有公因数

**示例:**

## 蟒蛇 3

```py
# Importing primes function
# From primePy Library
from primePy import primes

a = primes.phi(5)
print(a)

a = primes.phi(10)
print(a)
```

**输出:**

```py
4
4
```