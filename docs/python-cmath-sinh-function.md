# Python–cmath . sinh()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-sinh-function/](https://www.geeksforgeeks.org/python-cmath-sinh-function/)

**cmath** 是 python 内置模块，用于复数数学。cmath 模块有一个方法 sinh()，它返回传递给它的复数的双曲正弦值。

> **语法:** cmath.sinh(Z)
> 
> **参数:**只需要一个参数，即需要计算双曲正弦的数值。
> 
> **Return:** 返回一个复数，它是传递的数字的双曲正弦。

****例 1:****

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.sinh(5 + 3j))
```

****输出:****

```
(-73.46062169567368+10.472508533940392j) 
```

****示例 2:** 在此示例中，传递了实数，但返回的结果仍然是复数。**

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.sinh(1))
```

****输出:****

```
(1.1752011936438014+0j) 
```

****示例 3:** 在本例中，没有传递任何参数，在这种情况下，将引发 TypeError**

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.sinh())
```

****输出:****

```
TypeError: sinh() takes exactly one argument (0 given) 
```