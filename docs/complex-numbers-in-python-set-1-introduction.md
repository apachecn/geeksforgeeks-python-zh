# Python 中的复数|集合 1(简介)

> 原文:[https://www . geesforgeks . org/complex-numbers-in-python-set-1-introduction/](https://www.geeksforgeeks.org/complex-numbers-in-python-set-1-introduction/)

不仅是实数，Python 还可以使用文件“cmath”处理复数及其相关函数。复数在许多与数学相关的应用中有其用途，python 提供了有用的工具来处理和操纵它们。

**将实数转换为复数**

一个复数用“ **x + yi** 表示。Python 使用函数**复数(x，y)** 将实数 x 和 y 转换为复数。实部可以使用功能**实部()**访问，虚部可以用 **imag()** 表示。

```
# Python code to demonstrate the working of
# complex(), real() and imag()

# importing "cmath" for complex number operations
import cmath

# Initializing real numbers
x = 5
y = 3

# converting x and y into complex number
z = complex(x,y);

# printing real and imaginary part of complex number
print ("The real part of complex number is : ",end="")
print (z.real)

print ("The imaginary part of complex number is : ",end="")
print (z.imag)
```

输出:

```
The real part of complex number is : 5.0
The imaginary part of complex number is : 3.0

```

**复数相位**

在几何学上，复数的相位是正实轴和表示复数的向量之间的**角。这也被称为复数的**论证**。相位使用**相位()**返回，以复数为自变量。相位范围从**-π到+π。**即从 **-3.14 到+3.14** 。**

```
# Python code to demonstrate the working of
# phase()

# importing "cmath" for complex number operations
import cmath

# Initializing real numbers
x = -1.0
y = 0.0

# converting x and y into complex number
z = complex(x,y);

# printing phase of a complex number using phase()
print ("The phase of complex number is : ",end="")
print (cmath.phase(z))
```

输出:

```
The phase of complex number is : 3.141592653589793

```

**从极坐标形式转换为矩形形式，反之亦然**

转换为极坐标使用**极坐标()**完成，返回表示**模数 r** 和相位**角度 ph** 的**对(r，ph)** 。模量可以使用 **abs()** 显示，相位可以使用 **phase()** 显示。
一个复数用 **rect(r，ph)** 转换成直角坐标，其中 **r 为模数**， **ph 为相角**。它返回一个数值，数值等于 **r *(数学. cos(ph) +数学. sin(ph)*1j)**

```
# Python code to demonstrate the working of
# polar() and rect()

# importing "cmath" for complex number operations
import cmath
import math

# Initializing real numbers
x = 1.0
y = 1.0

# converting x and y into complex number
z = complex(x,y);

# converting complex number into polar using polar()
w = cmath.polar(z)

# printing modulus and argument of polar complex number
print ("The modulus and argument of polar complex number is : ",end="")
print (w)

# converting complex number into rectangular using rect()
w = cmath.rect(1.4142135623730951, 0.7853981633974483)

# printing rectangular form of complex number
print ("The rectangular form of complex number is : ",end="")
print (w)
```

输出:

```
The modulus and argument of polar complex number is : (1.4142135623730951, 0.7853981633974483)
The rectangular form of complex number is : (1.0000000000000002+1j)

```

[Python 中的复数|集合 2(重要函数和常数)](https://www.geeksforgeeks.org/complex-numbers-python-set-2-important-functions-constants/)

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。