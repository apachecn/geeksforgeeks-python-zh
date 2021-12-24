# Python–cmath . acosh()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-acosh-function/](https://www.geeksforgeeks.org/python-cmath-acosh-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.acosh()** 函数返回复数的反双曲余弦值。该函数传递的值可以是**整数、浮点数、**和**复数。**

> ***语法:** cmath.acosh(x)*
> 
> ***参数:**此方法只接受单个参数。*
> 
> *   ***x :** 该参数是要传递给 acosh()* 的值
> 
> ***返回:**该函数返回一个*复数*的*反双曲*值。*

下面的例子说明了上述功能的使用:

**示例#1 :** 在这个示例中，我们可以看到，通过使用 *cmath.acosh()* 方法，我们能够通过向其传递任何值来获得反双曲的值。

## 蟒蛇 3

```
# Python code to implement
# the acosh()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.acosh() method 
val = cmath.acosh(3) 

print(val)
```

**输出:**

```
(1.762747174039086+0j)
```

**例 2:**

## 蟒蛇 3

```
# Python code to implement
# the acosh()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.acosh() method 
val = cmath.acosh(2 + 5j) 

print(val)
```

**输出:**

```
(2.3830308809003258+1.1961255219693696j)
```