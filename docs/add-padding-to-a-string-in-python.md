# 在 Python 中给字符串添加填充

> 原文:[https://www . geesforgeks . org/add-padding-to-a-string-in-python/](https://www.geeksforgeeks.org/add-padding-to-a-string-in-python/)

向字符串中插入非信息字符称为填充。插入可以在字符串的任何地方进行。字符串填充对于打印时字符串的输出格式和对齐非常有用。即使显示像表字符串这样的值，也需要填充。

### 不同类型的填充

三种最常用的字符串填充技术是:

*   在字符串的末尾插入一个字符，使其具有指定的长度，称为**左填充**。当命名以数字字符开始的文件时，它非常有用，这些字符是按顺序生成的。
*   在**居中填充**的情况下，所需的字符以相等的次数插入到字符串的两端，直到新形成的字符串具有特定的长度。这将使特定或所需长度的字符串居中。这将返回一个以长度和宽度为中心的字符串。这里，默认字符是空格。
*   在**右填充**中，给定的字符被插入到需要填充的字符串的右侧。指定的字符被添加到字符串的末尾，直到它达到所需的长度。

填充可以使用各种内置函数来实现，下面将通过一个示例来讨论每一个函数:

### 光源()

使用此方法，通过在字符串的右端插入填充来将字符串向左对齐。

> **语法**字符串.光源(宽度，char)
> 
> **参数:**
> 
> *   **宽度**-填充完成后的弦长。强制的。
> *   **字符**–要填充的字符串，可选。
> 
> **返回:**返回指定宽度长度后剩余的字符串。

**例**

## 蟒蛇 3

```
# Creating a string variable
str = "Geeks for Geeks"

# Printing the output of ljust() method
print(str.ljust(20, '0'))
```

**输出:**

```
Geeks for Geeks00000
```

### rjust（）

使用此方法，通过在字符串的左端插入字符来将字符串向右对齐。

> **语法:** string.rjust(宽度，字符)
> 
> **参数:**
> 
> *   **宽度**-填充完成后的弦长。强制的。
> *   **字符**–要填充的字符串，可选。
> 
> **返回:**返回一个字符串，该字符串放置在右侧，字符插入到开头和结尾。

**示例:**

## 蟒蛇 3

```
# Creating a string variable
str = "Geeks for Geeks"

# Using rjust() method
print(str.rjust(20, "O"))
```

**输出:**

```
OOOOOGeeks for Geeks
```

### 中心()

**center()** 方法以字符串为参数，以给定宽度在中心对齐。

> **语法:**字符串.中心(宽度)
> 
> **参数:**
> 
> 这个方法只接受一个参数，即宽度，并在两端加上空格。
> 
> **返回:**
> 
> 返回填充到中间的字符串。

**示例:**

## 蟒蛇 3

```
# Creating a string variable
str = "Geeks for Geeks"

# Using center() method
print("Center String: ", str.center(20))
```

**输出:**

```
Center String:    Geeks for Geeks
```

### zfill（）

**zfill()** 方法在字符串的开头插入 0。此方法通过在字符串的左侧插入 0 字符来填充右侧，直到字符串达到特定长度。如果传递的参数小于字符串的长度或大小，则不进行填充。

> **语法:** string.zfill(长度)
> 
> **参数:**以长度为唯一参数。

**示例:**

## 蟒蛇 3

```
# Creating string variables
v1 = "Geeks"
v2 = "for"
v3 = "Geeks"

# Using zfill() method
print(v1.zfill(10))
print(v2.zfill(10))
print(v3.zfill(10))
```

**输出:**

```
00000Geeks
0000000for
00000Geeks
```

### 格式()

**格式()**方法可用于所有类型的划水，即左、右和中。

> **语法:** string.format(value_1，value_2，value_3，value_4… value_n)
> 
> **参数:**要格式化的特定值。占位符可以是索引，也可以只是空白。
> 
> **返回:**一个格式化的字符串

**示例:**

## 蟒蛇 3

```
# Creating string variable
str = "Cost of mask: {price:.2f} Rupees."

# Using format() method
print(str.format(price=20))
```

**输出:**

```
Cost of mask: 20.00 Rupees.
```