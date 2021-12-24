# Python–cmath . tan()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-tan-function/](https://www.geeksforgeeks.org/python-cmath-tan-function/)

**cmath** 是 Python 内置模块，用于复数数学。cmath 模块有一个方法 tan()，它返回传递给它的复数的正切值。

> **语法:** cmath.tan(Z)
> 
> **参数:**只需要一个参数，即需要计算正切的数值。
> 
> **Return:** 返回一个复数，它是传递的数字的正切值。

****例 1:****

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.tan(5 + 3j))
```

****输出:****

```
(-0.002708235836224072+1.0041647106948153j) 
```

****示例 2:** 在此示例中，传递了实数，但返回的结果仍然是复数。**

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.tan(1))
```

****输出:****

```
(1.5574077246549023+0j) 
```

****示例 3:** 在本例中，没有传递任何参数，在这种情况下，将引发 TypeError**

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.tan())
```

****输出:****

```
TypeError: tan() takes exactly one argument (0 given) 
```