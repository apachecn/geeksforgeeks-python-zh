# Python–cmath . polar()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-polar-function/](https://www.geeksforgeeks.org/python-cmath-polar-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.polar()** 函数用于将复数转换为极坐标。该函数传递的值可以是**整数、浮点数、**和**复数。**

> ***语法:*** cmath.polar(x)
> 
> ***参数:**该方法接受以下参数。*
> 
> *   ***x :** 这个参数是求极坐标的*数。
> 
> ***返回:**这个*方法返回一个代表极坐标的元组值。

下面的例子说明了上述功能的使用:

**示例#1 :**

## 蟒蛇 3

```
# Python code to implement
# the polar()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.polar() method 
val = cmath.polar(1) 
print(val)
```

**输出:**

```
(1.0, 0.0)
```

**例 2:**

## 蟒蛇 3

```
# Python code to implement
# the polar()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.polar() method 
val = cmath.polar(2 + 4j)
print(val)
```

**输出:**

```
(4.47213595499958, 1.1071487177940904)
```