# Python–cmath . atanh()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-atanh-function/](https://www.geeksforgeeks.org/python-cmath-atanh-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.atanh()** 函数返回复数的反双曲反正切值。该函数传递的值可以是**整数、浮点数、**和**复数。**

> **语法:** cmath。阿坦 *(x)*
> 
> ***参数:**此方法只接受单个参数。*
> 
> *   ***x :** 该参数是要传递给* atanh *()* 的值
> 
> ***返回:**该函数返回一个*复数的反双曲反正切*值。*

下面的例子说明了上述功能的使用:

**示例#1 :** 在本例中，我们可以通过使用 *cmath 看到这一点。*阿坦赫 *()* 方法，我们能够通过传递任何值给它来获得反双曲反正切的值。

## 蟒蛇 3

```
# Python code to implement
# the atanh()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.atanh() method 
val = cmath.atanh(3) 

print(val)
```

**输出:**

```
(0.34657359027997264+1.5707963267948966j)

```

**例 2:**

## 蟒蛇 3

```
# Python code to implement
# the atanh()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.atanh() method 
val = cmath.atanh(2 + 5j) 

print(val)
```

**输出:**

```
(0.06706599664866984+1.399284356584545j)

```