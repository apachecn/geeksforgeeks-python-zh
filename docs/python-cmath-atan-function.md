# Python–cmath . atan()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-atan-function/](https://www.geeksforgeeks.org/python-cmath-atan-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.atan()** 函数返回复数的反正切值。该函数传递的值可以是**整数、浮点数、**和**复数。**

> **语法:** cmath。阿坦 *(x)*
> 
> ***参数:**此方法只接受单个参数。*
> 
> *   ***x :** 该参数是传递给* atan *()* 的值
> 
> ***返回:**该函数返回一个*复数*的*反正切*值。*

下面的例子说明了上述功能的使用:

**示例#1 :** 在本例中，我们可以通过使用 *cmath 看到这一点。*在 *()* 方法中，我们可以通过向反正切传递任何值来获得它的值。

## 蟒蛇 3

```py
# Python code to implement
# the atan()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.atan() method 
val = cmath.atan(3) 

print(val)
```

**输出:**

```py
(1.2490457723982544+0j)

```

**例 2:**

## 蟒蛇 3

```py
# Python code to implement
# the atan()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.atan() method 
val = cmath.atan(2 + 5j) 

print(val)
```

**输出:**

```py
(1.4998477994928145+0.17328679513998632j)

```