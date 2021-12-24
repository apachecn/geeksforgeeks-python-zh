# Python 中的 atan2()函数

> 原文:[https://www.geeksforgeeks.org/atan2-function-python/](https://www.geeksforgeeks.org/atan2-function-python/)

**atan2(y，x)** 以弧度为单位返回 atan(y/x)的值。atan2()方法返回一个介于–![\pi](img/e43e09d6003d9d39fa5266475445a72c.png "Rendered by QuickLaTeX.com")和![\pi](img/e43e09d6003d9d39fa5266475445a72c.png "Rendered by QuickLaTeX.com")之间的数值，代表(x，y)点和正 x 轴的角度![\theta](img/5a47c79344ecb82823a74b87e4a14bb8.png "Rendered by QuickLaTeX.com")。

**语法:**

```
atan2(y, x)
```

**参数:**

```
(y, x) - Both must be a numeric value.
```

**返回:**

```
Returns atan(y / x), in radians.
The double value is  from polar coordinate (r, theta). 
```

**类型错误:**

```
Returns a TypeError if anything other than float is passed. 
```

**代码#1 :**

```
# Python3 program to demonstrate
# the atan2() method 

# imports math 
import math

# prints the theta value of
# two negative co-ordinates 
theta1 = math.atan2(-0.9, -0.9) 
print("atan2(-0.9, -0.9) : ", theta1) 

# prints the theta value of
# two positive co-ordinates 
theta2 = math.atan2(1.2, 1.5) 
print("atan2(1.2, 1.5) : ", theta2) 

# prints the theta value of one
# positive and one negative co-ordinates 
theta3 = math.atan2(1.2, -1.5) 
print("atan2(1.2, -1.5):", theta3)
```

**输出:**

```
atan2(-0.5, -0.5): -2.356194490192345
atan2(1.2, 1.5): 0.6747409422235526
atan2(1.2, -1.5): 2.4668517113662407

```

**代码#2 :**

```
# Python3 program to demonstrate the atan() method 

# imports math 
import math

# list containing x and y coordinates 
y = [1, 2, 3, 4] 
x = [6, 3, 7, 8] 

# traversing in range to get theta 
# for all y and x co-ordinates 
for i in range(len(x)):
    theta = math.atan2(y[i], x[i]) 
    print(theta) 
```

**输出:**

```
0.16514867741462683
0.5880026035475675
0.40489178628508343
0.4636476090008061

```

**代码#3 :** 程序演示错误

```
# Python3 program to demonstrate the  
# TypeError in atan() method 

# importing math 
import math

y, x = 3, 6

# when integer values are passed 
# it returns a TypeError
theta = math.atan2([y], [x]) 
print(theta)
```

**输出:**

```
Traceback (most recent call last):
  File "/home/622586ab389561bcdbfff258aca01e65.py", line 9, in 
    theta = math.atan2([y],[x]) 
TypeError: a float is required

```

**实际应用:**
这个函数用来求给定 Y 和 X 坐标时的弧度斜率。

**代码#4 :**

```
# Let's find the slope when X
# and Y co-ordinates are given 

# imports math 
import math

# X and Y are co-ordinates
X = 2; Y = 2 

# slope in radians 
theta1 = math.atan2(Y, X) 

# print the Slope in radians
print(theta1)
```

**输出:**

```
0.7853981633974483

```