# 将 Python 字符串转换为浮点数据类型

> 原文:[https://www . geesforgeks . org/convert-python-string-to-float-datatype/](https://www.geeksforgeeks.org/convert-python-string-to-float-datatype/)

让我们看看如何将字符串对象转换成浮点对象。我们可以通过使用以下功能来做到这一点:

*   浮动()
*   十进制()

**方法一:使用`float()`**

```
# declaring a string
str1 = "9.02"
print("The initial string : " + str1)
print(type(str1)) 

# converting into float
str2 = float(str1)
print("\nThe conversion of string to float is ", str2)
print(type(str2)) 

# performing an operation on the float variable
str2 = str2 + 1
print("The converted string to float is incremented by 1 : ", str2)
```

**输出:**

```
The initial string : 9.02
<type 'str'>

The conversion of string to float is  9.02
<type 'float'>
The converted string to float is incremented by 1 :  10.02

```

**方法二:使用`decimal()`** :因为我们只要一个带有十进制数值的字符串，所以这个方法也可以使用。

```
# importing the module
from decimal import Decimal

# declaring a string
str1 = "9.02"
print("The initial string : " + str1)
print(type(str1)) 

# converting into float
str2 = Decimal(str1)
print("\nThe conversion of string to float is ", str2)
print(type(str2)) 

# performing an operation on the float variable
str2 = str2 + 1
print("The converted string to float is incremented by 1 : ", str2)
```

**输出:**

```
The initial string : 9.02
<type 'str'>

The conversion of string to float is  9.02
<type 'float'>
The converted string to float is incremented by 1 :  10.02

```