# Python 中的度()和弧度()

> 原文:[https://www . geesforgeks . org/python 中的度和弧度/](https://www.geeksforgeeks.org/degrees-and-radians-in-python/)

degress()和 radians()是 Python 3 和 Python 2 中数学模块中指定的方法。

通常人们需要处理弧度到度数的转换的数学计算，反之亦然，尤其是在几何领域。Python 提供了处理这一功能的内置方法。本文将讨论这两种功能。

**radians()**

该函数接受“**度**”作为输入，并将其转换为等效弧度。

> 语法:**弧度(度)**
> 
> **参数:**
> **度:**需要转换成弧度的度数值
> 
> **返回:**该函数返回与自变量等价的浮点弧度。
> **计算当量:** 1 弧度= 180/π度。

**代码#1 :** 演示弧度()

```
# Python code to demonstrate
# working of radians()

# for radians
import math

# Printing radians equivalents.
print("180 / pi Degrees is equal to Radians : ", end ="")
print (math.radians(180 / math.pi))

print("180 Degrees is equal to Radians : ", end ="")
print (math.radians(180))

print("1 Degrees is equal to Radians : ", end ="")
print (math.radians(1))
```

输出:

```
180/pi Degrees is equal to Radians : 1.0
180 Degrees is equal to Radians : 3.141592653589793
1 Degrees is equal to Radians : 0.017453292519943295

```

**degrees()**

该函数接受“**弧度**”作为输入，并将其转换为等效度数。

> 语法:**度(rad)**
> 
> **参数:**
> **弧度:**需要转换成度数的弧度值。
> 
> **返回:**该函数返回与参数等价的浮点度数。
> **计算等效:** 1 度=π/180 弧度。

**代码#2 :** 演示度()

```
# Python code to demonstrate
# working of degrees()

# for degrees()
import math

# Printing degrees equivalents.
print("pi / 180 Radians is equal to Degrees : ", end ="")
print (math.degrees(math.pi / 180))

print("180 Radians is equal to Degrees : ", end ="")
print (math.degrees(180))

print("1 Radians is equal to Degrees : ", end ="")
print (math.degrees(1))
```

输出:

```
pi/180 Radians is equal to Degrees : 1.0
180 Radians is equal to Degrees : 10313.240312354817
1 Radians is equal to Degrees : 57.29577951308232

```

**应用:**
这些函数在几何相关的数学计算中有很多可能的应用，在天文计算中也有一定的应用。