# Python–cmath . isclose()函数

> 原文:[https://www . geesforgeks . org/python-cmath-is close-function/](https://www.geeksforgeeks.org/python-cmath-isclose-function/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.isclose()** 函数用于检查两个复数值是否接近。该函数传递的值可以是**整数、浮点数、**和**复数。**

> ***语法:*** cmath.isclose(a，b，rel_tol =值，abs_tol =值)
> 
> ***参数:**该方法接受以下参数。*
> 
> *   ***a :** 该参数是*第一个检查接近度的值。
> *   **b** :该参数是检查紧密度的第二个值。
> *   **rel_tol =值**:该参数是 a 值和 b 值之间允许的最大差值。
> *   **abs_tol =值:**此参数为最小绝对公差
> 
> ***返回:**这个*方法返回一个布尔值。

下面的例子说明了上述功能的使用:

**示例#1 :**

## 蟒蛇 3

```py
# Python code to implement
# the isclose()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.isclose() method 
val = cmath.isclose(1 + 2j, 1 + 2j) 
print(val) 

val1 = cmath.isclose(1 + 2.2j, 1 + 2j) 
print(val1)
```

**输出:**

```py
True
False
```

**例 2:**

## 蟒蛇 3

```py
# Python code to implement
# the isclose()function

# importing "cmath"
# for mathematical operations  
import cmath 

# using cmath.isclose() method 
val = cmath.isclose(1 + 2j, 1 + 2j, abs_tol = 0.5) 
print(val) 

val1 = cmath.isclose(1 + 2.2j, 1 + 2j, abs_tol = 0.5) 
print(val1)
```

**输出:**

```py
True
True

```