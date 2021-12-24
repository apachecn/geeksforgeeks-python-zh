# Python–cmath . cosh()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-cosh-function/](https://www.geeksforgeeks.org/python-cmath-cosh-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.cosh()** 函数返回复数的双曲余弦值。该函数传递的值可以是**整数、浮点数、**和**复数。**

> ***语法:** cmath。* cosh *(x)*
> 
> ***参数:**此方法只接受单个参数。*
> 
> *   ***x :** 该参数是传递给* cosh *()* 的值
> 
> ***返回:**该函数返回一个*复数*的*双曲余弦*值。*

下面的例子说明了上述功能的使用:

**示例#1 :** 在本例中，我们可以通过使用 *cmath 看到这一点。* cosh *()* 方法，我们能够通过传递任何值给它来获得双曲余弦的值。

## 蟒蛇 3

```py
# Python code to implement
# the cosh()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.cosh() method 
val = cmath.cosh(3) 

print(val)
```

**输出:**

```py
(10.067661995777765+0j)
```

**例 2:**

## 蟒蛇 3

```py
# Python code to implement
# the cosh()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.cosh() method 
val = cmath.cosh(2 + 5j) 

print(val)
```

**输出:**

```py
(2.37054853731792+1.184231684275022j)
```