# Python–cmath . is inite()函数

> 原文:[https://www . geesforgeks . org/python-cmath-is inite-function/](https://www.geeksforgeeks.org/python-cmath-isfinite-function/)

**cMath 模块**包含许多用于复数数学运算的函数。**cmath . is inite()**函数用于检查该值是否有限。该函数传递的值可以是**整数、浮点数、**和**复数。**

> ***语法:*** cmath.isfinite(x)
> 
> ***参数:**该方法接受以下参数。*
> 
> *   ***x :** 此参数是要检查是否有限的*值。
> 
> ***返回:**这个*方法返回一个布尔值。

下面的例子说明了上述功能的使用:

**示例#1 :**

## 蟒蛇 3

```
# Python code to implement
# the isfinite()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.isfinite() method 
val = cmath.isfinite(1 + 2j) 
print(val)
```

**输出:**

```
True

```

**例 2:**

## 蟒蛇 3

```
# Python code to implement
# the isfinite()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.isfinite() method 
val = cmath.isfinite(complex(3.0, float('inf')))
print(val)
```

**输出:**

```
False

```