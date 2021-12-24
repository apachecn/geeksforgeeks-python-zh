# Python–cmath . sin()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-sin-function/](https://www.geeksforgeeks.org/python-cmath-sin-function/)

**cmath** 是 Python 内置模块，用于复数数学。cmath 模块有一个方法 sin()，它返回传递给它的复数的正弦值。

> **语法:** cmath.sin(Z)
> 
> **参数:**只需要一个参数，即需要计算正弦的数值。
> 
> **返回:**返回一个复数，该复数是传递的数字的正弦值。

****例 1:****

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.sin(5 + 3j))
```

****输出:****

```
(-9.654125476854839+2.841692295606352j) 
```

****示例 2:** 在此示例中，传递了实数，但返回的结果仍然是复数。**

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.sin(1))
```

****输出:****

```
(0.8414709848078965+0j) 
```

****示例 3:** 在本例中，没有传递任何参数，在这种情况下，将引发 TypeError**

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.sin())
```

****输出:****

```
TypeError: sin() takes exactly one argument (0 given) 
```