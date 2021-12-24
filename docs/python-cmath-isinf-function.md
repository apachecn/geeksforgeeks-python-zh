# Python–cmath . isinf()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-isinf-function/](https://www.geeksforgeeks.org/python-cmath-isinf-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.isinf()** 函数用于检查值是否为正无穷大或负无穷大。该函数传递的值可以是**整数、浮点数、**和**复数。**

> ***语法:*** cmath.isinf(x)
> 
> ***参数:**该方法接受以下参数。*
> 
> *   ***x :** 该参数是检查无穷大的*值。
> 
> ***返回:**这个*方法返回一个布尔值。

下面的例子说明了上述功能的使用:

**示例#1 :**

## 蟒蛇 3

```
# Python code to implement
# the isinf()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.isinf() method 
val = cmath.isinf(1 + 2j) 
print(val)
```

**输出:**

```
False
```

**例 2:**

## 蟒蛇 3

```
# Python code to implement
# the isinf()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.isinf() method 
val = cmath.isinf(complex(1 + float('inf'))) 
print(val)
```

**输出:**

```
True

```