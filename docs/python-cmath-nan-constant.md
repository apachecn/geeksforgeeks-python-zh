# Python | cmath.nan 常量

> 原文:[https://www.geeksforgeeks.org/python-cmath-nan-constant/](https://www.geeksforgeeks.org/python-cmath-nan-constant/)

**cMath 模块**包含许多用于复数数学运算的函数。 **cmath.nan** 常量用于获取浮点 nan(不是数字)。

> ***语法:*** cmath.nan
> 
> ***返回:*** 返回浮点 nan 值。

下面的例子说明了上述功能的使用:

**示例#1 :**

## 蟒蛇 3

```
# Python code to implement
# the cmath.nan constant

# importing "cmath"
# for mathematical operations  
import cmath 

# Print the value of nan
val = cmath.nan 
print(val)
```

**输出:**

```
nan

```

**例 2:**

## 蟒蛇 3

```
# Python code to implement
# the cmath.nan constant

# importing "cmath"
# for mathematical operations  
import cmath 

# use of cmath.nan
val = cmath.isnan(cmath.nan)
print(val)
```

**输出:**

```
True

```