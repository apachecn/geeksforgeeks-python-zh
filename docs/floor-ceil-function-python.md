# 地板()和天花板()功能 Python

> 原文:[https://www.geeksforgeeks.org/floor-ceil-function-python/](https://www.geeksforgeeks.org/floor-ceil-function-python/)

### **楼层()功能:**

Python 中的 floor()方法返回 x 的 floor，即不大于 x 的最大整数。

```py
Syntax:
import math
math.floor(x)

Parameter: 
x-numeric expression. 

Returns: 
largest integer not greater than x.
```

下面是 floor()方法的 Python 实现:

## 计算机编程语言

```py
# Python program to demonstrate the use of floor() method

# This will import math module
import math   

# prints the ceil using floor() method
print "math.floor(-23.11) : ", math.floor(-23.11)
print "math.floor(300.16) : ", math.floor(300.16)
print "math.floor(300.72) : ", math.floor(300.72)
```

**输出:**

```py
math.floor(-23.11) :  -24.0
math.floor(300.16) :  300.0
math.floor(300.72) :  300.0
```

### **天花板()功能:**

Python 中的天花板(x)方法返回 x 的天花板值，即大于或等于 x 的最小整数。

```py
Syntax: 
import math
math.ceil(x)

Parameter:
x:This is a numeric expression.

Returns: 
Smallest integer not less than x.
```

下面是 ceil()方法的 Python 实现:

## 计算机编程语言

```py
# Python program to demonstrate the use of ceil() method

# This will import math module
import math   

# prints the ceil using ceil() method
print "math.ceil(-23.11) : ", math.ceil(-23.11)
print "math.ceil(300.16) : ", math.ceil(300.16)
print "math.ceil(300.72) : ", math.ceil(300.72)
```

**输出:**

```py
math.ceil(-23.11) :  -23.0
math.ceil(300.16) :  301.0
math.ceil(300.72) :  301.0
```