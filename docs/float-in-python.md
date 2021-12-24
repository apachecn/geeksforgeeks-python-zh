# Python 中的 float()

> 原文:[https://www.geeksforgeeks.org/float-in-python/](https://www.geeksforgeeks.org/float-in-python/)

**Python float()函数**用于从一个数字或一个字符串返回一个浮点数。

> **语法:**浮点(x)

## **浮动()参数**

该方法只接受一个参数，该参数也是可选的。让我们看看各种类型的参数，该方法接受:

> **数字:**可以是整数，也可以是浮点数。
> 
> **一串:**
> 
> *   必须包含任何类型的数字。
> *   方法会忽略任何左边或右边的空格或新行。
> *   可以使用数学运算符。
> *   可以包含 NaN、Infinity 或 inf(任何情况下)

**float()方法可以根据传递的参数返回的值**

*   如果传递了参数，则返回等效的浮点数。
*   如果没有传递参数，则该方法返回 0.0。
*   如果传递的任何字符串不是小数点数字，或者与上面提到的任何情况都不匹配，则会出现错误。
*   如果一个数字超出了 Python 浮点的范围，那么就会生成 OverflowError。

## Python 中的浮点示例

### **示例 float()在 Python 中是如何工作的**

## 蟒蛇 3

```
# Python program to illustrate
# Various examples and working of float()
# for integers
print(float(21.89))

# for floating point numbers
print(float(8))

# for integer type strings
print(float("23"))

# for floating type strings
print(float("-16.54"))

# for string floats with whitespaces
print(float("     -24.45   \n"))

# for inf/infinity
print(float("InF"))
print(float("InFiNiTy"))

# for NaN
print(float("nan"))
print(float("NaN"))

# Error is generated at last
print(float("Geeks"))
```

**输出:**

```
21.89
8.0
23.0
-16.54
-24.45
inf
inf
nan
nan
```

所有行都正确执行，但最后一行将返回错误:

```
Traceback (most recent call last):
  File "/home/21499f1e9ca207f0052f13d64cb6be31.py", line 25, in 
    print(float("Geeks"))
ValueError: could not convert string to float: 'Geeks'
```

### **例 2: float()表示无穷大，Nan**

## 蟒蛇 3

```
# Python program to illustrate
# Various examples and working of float()

# for inf/infinity
print(float("InF"))
print(float("InFiNiTy"))

# for NaN
print(float("nan"))
print(float("NaN"))
```

**输出:**

```
inf
inf
nan
nan
```

### **示例 3:在 Python 中将整数转换为浮点数**

## 蟒蛇 3

```
# python code to convert int
# float
number = 90
result = float(number)

print(result)
```

**输出:**

```
90.0
```

### 示例 **4:在 Python 中将字符串转换为浮点数**

## 蟒蛇 3

```
# python code to convert string
# to float
string = "90"
result = float(string)

print(result)
```

**输出:**

```
90.0
```

### **示例 5: P** ython float()异常

## 蟒蛇 3

```
number = "geeks"
try:
    print(float(number))
except ValueError as e:
    print(e)
```

**输出:**

```
could not convert string to float: 'geeks'
```