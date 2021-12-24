# Python 中的 abs()

> 原文:[https://www.geeksforgeeks.org/abs-in-python/](https://www.geeksforgeeks.org/abs-in-python/)

**Python abs()函数**用于返回一个数字的绝对值，即它会去掉数字的负号。

> **语法:**ABS(number)
> **number:**可以是整数、浮点
> 
> 数字或复数

abs()只接受一个参数，一个要返回绝对值的数字。参数可以是整数、浮点数或复数。

*   如果参数是整数或浮点数，abs()将以整数或浮点数形式返回绝对值。
*   对于复数，abs()只返回幅度部分，也可以是浮点数。

## Python 中的 abs()函数是做什么的？

abs()函数使任何负数变为正数，而正数不受影响。任何数字的绝对值总是正的。对于任何正数，绝对值是数字本身，对于任何负数，绝对值是(-1)乘以负数。

### 示例 1: Python abs()函数示例

在这个例子中，我们将 float、int 和 complex 数据传递给 abs()函数，它将返回绝对值。

## 蟒蛇 3

```
# Python code to illustrate
# abs() built-in function

# floating point number
float = -54.26
print('Absolute value of float is:', abs(float))

# An integer
int = -94
print('Absolute value of integer is:', abs(int))

# A complex number
complex = (3 - 4j)
print('Absolute value or Magnitude of complex is:', abs(complex))
```

**输出:**

```
Absolute value of float is: 54.26
Absolute value of integer is: 94
Absolute value or Magnitude of complex is: 5.0
```

### 示例 2:绝对值 Python，距离计算

该等式显示了速度、行驶距离和所用时间之间的关系:

> 速度是距离除以时间。

而且我们知道速度、时间和距离从来不是负数，为此我们将使用 abs()方法来计算精确的时间、距离和速度。

**使用的公式:**

```
Distance  = Speed * Time
Time = Distance / Speed
Speed = Distance / Time
```

**示例:**

```
Input : distance(km) : 48.5  time(hr) : 2.6
Output : Speed(km / hr) : 18.653846153

Input : speed(km / hr) : 46.0  time(hr) : 3.2
Output : Distance(km) : 147.2

Input : distance(km) : 48.5  speed(km / hr) : 46.0
Output : Time(hr) : 1.0543
```

**代码:**

## 蟒蛇 3

```
# Python3 Program to calculate speed,
# distance and time

# Function to calculate speed
def cal_speed(dist, time):
    print(" Distance(km) :", dist)
    print(" Time(hr) :", time)
    return dist / time

# Function to calculate distance traveled
def cal_dis(speed, time):
    print(" Time(hr) :", time)
    print(" Speed(km / hr) :", speed)
    return speed * time

# Function to calculate time taken
def cal_time(dist, speed):
    print(" Distance(km) :", dist)
    print(" Speed(km / hr) :", speed)
    return speed * dist

# Driver Code
# Calling function cal_speed()
print(" The calculated Speed(km / hr) is :",
      cal_speed(abs(45.9), abs(2.0)))
print("")

# Calling function cal_dis()
print(" The calculated Distance(km) :",
      cal_dis(abs(62.9), abs(2.5)))
print("")

# Calling function cal_time()
print(" The calculated Time(hr) :",
      cal_time(abs(48.0), abs(4.5)))
```

**输出:**

```
 Distance(km) : 45.9
 Time(hr) : 2.0
 The calculated Speed(km / hr) is : 22.95

 Time(hr) : 2.5
 Speed(km / hr) : 62.9
 The calculated Distance(km) : 157.25

 Distance(km) : 48.0
 Speed(km / hr) : 4.5
 The calculated Time(hr) : 216.0
```