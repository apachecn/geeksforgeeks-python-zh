# Python–cmath . phase()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-phase-function/](https://www.geeksforgeeks.org/python-cmath-phase-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.phase()** 函数用于获取复数的相位。该函数传递的值可以是**整数、浮点数、**和**复数。**

> ***语法:*** cmath.phase(x)
> 
> ***参数:**该方法接受以下参数。*
> 
> *   ***x :** 这个参数就是*号要找的相位。
> 
> ***返回:**这个*方法返回一个代表复数相位的浮点值。

下面的例子说明了上述功能的使用:

**示例#1 :**

## 蟒蛇 3

```
# Python code to implement
# the phase()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.phase() method 
val = cmath.phase(1) 
print(val)
```

**输出:**

```
0.0
```

**例 2:**

## 蟒蛇 3

```
# Python code to implement
# the phase()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.phase() method 
val = cmath.phase(1 + 4j)
print(val)
```

**输出:**

```
1.3258176636680326
```