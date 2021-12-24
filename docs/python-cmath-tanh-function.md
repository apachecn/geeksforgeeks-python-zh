# Python–cmath . tanh()函数

> 原文:[https://www.geeksforgeeks.org/python-cmath-tanh-function/](https://www.geeksforgeeks.org/python-cmath-tanh-function/)

**cmath** 是 Python 内置模块，用于复数数学。cmath 模块有一个方法 tanh()，它返回传递给它的复数的双曲正切值。

> **语法:** cmath.tanh(Z)
> 
> **参数:**只需要一个参数，即需要计算双曲正切的数值。
> 
> **Return:** 返回一个复数，它是传递的数字的双曲正切值。

****例 1:****

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.tanh(1 + 5j))
```

****输出:****

```
(1.2407479829240697-0.18610947764730415j) 
```

****示例 2:** 在此示例中，传递了实数，但返回的结果仍然是复数。**

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.tanh(1))
```

****输出:****

```
(0.7615941559557649+0j) 
```

****示例 3:** 在本例中，没有传递任何参数，在这种情况下，将引发 TypeError**

## **蟒蛇 3**

```
# Import the Library
import cmath 

# Printing the result
print (cmath.tanh())
```

****输出:****

```
TypeError: tanh() takes exactly one argument (0 given) 
```