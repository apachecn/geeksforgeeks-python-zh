# Python–cmath . cos()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-cos-function/](https://www.geeksforgeeks.org/python-cmath-cos-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.cos()** 函数返回复数的余弦值。该函数传递的值可以是**整数、浮点数、**和**复数。**

> ***语法:** cmath。* cos *(x)*
> 
> ***参数:**此方法只接受单个参数。*
> 
> *   ***x :** 该参数是传递给* cos *()* 的值
> 
> ***返回:**该函数返回一个*复数*的*余弦*值。*

下面的例子说明了上述功能的使用:

**示例#1 :** 在本例中，我们可以通过使用 *cmath 看到这一点。* cos *()* 方法，我们可以通过传递任何值给它来得到余弦值。

## 蟒蛇 3

```
# Python code to implement
# the cos()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.cos() method 
val = cmath.cos(3) 

print(val)
```

**输出:**

```
(-0.9899924966004454-0j)
```

**例 2:**

## 蟒蛇 3

```
# Python code to implement
# the cos()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.cos() method 
val = cmath.cos(2 + 5j) 

print(val)
```

**输出:**

```
(-30.88223531891674-67.47278844058752j)
```