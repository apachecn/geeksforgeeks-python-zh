# Python–cmath . asin()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-asin-function/](https://www.geeksforgeeks.org/python-cmath-asin-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.asin()** 函数返回复数的反正弦值。该函数传递的值可以是**整数、浮点数、**和**复数。**

> ***语法:** cmath。* asin *(x)*
> 
> ***参数:**此方法只接受单个参数。*
> 
> *   ***x :** 该参数是传递给 *()* 的值*
> 
> ***返回:**该函数返回一个*复数*数的反正弦值。*

下面的例子说明了上述功能的使用:

**示例#1 :** 在本例中，我们可以通过使用 *cmath 看到这一点。*作为 *()* 方法，我们可以通过向其传递任何值来获得*反正弦*的值。

## 蟒蛇 3

```
# Python code to implement
# the asin()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.asin() method 
val = cmath.asin(3) 

print(val)
```

**输出:**

```
(1.5707963267948966+1.762747174039086j)

```

**例 2:**

## 蟒蛇 3

```
# Python code to implement
# the asin()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.asin() method 
val = cmath.asin(2 + 5j) 

print(val)
```

**输出:**

```
(0.374670804825527+2.3830308809003258j)

```