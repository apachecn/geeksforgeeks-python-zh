# 如何用 Python 去掉一个数字的所有小数？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 从数字中移除所有小数/](https://www.geeksforgeeks.org/how-to-remove-all-decimals-from-a-number-using-python/)

在 python 编程中，有时需要从一个数字中移除所有小数才能获得所需的输出。这些小数在 Python 中也称为浮点数。基本上，python 中有 3 种数字数据类型。它们是整数(int())、浮点数(float())和复数(complex())数据类型。python 中的类型转换有助于将十进制数值(浮点数)转换为整数。因此，转换 float->int 会删除数字中的所有小数。

有三种方法可以使用 python 删除数字中的所有小数

**方法:**

1.  使用 int()函数
2.  使用 trunc()函数
3.  使用拆分( )函数

**方法 1:使用 int()【类型转换】:**

int()是一个内置函数，用于将任何值转换为整数。

## 蟒 3

```
Number1 = 44.560
Number2 = 856.9785623
Number3 = 9999.99

# Type conversion float to int
New_Number1 = int(Number1)
New_Number2 = int(Number2)
New_Number3 = int(Number3)

print("Number1 = ", New_Number1)
print("Number2 = ", New_Number2)
print("Number3 = ", New_Number3)

# type() function returns the data type
print(type(Number1))
print(type(New_Number1))
```

**输出:**

```
Number1 =  44
Number2 =  856
Number3 =  9999
<class 'float'>
<class 'int'>
```

**方法二:使用截断函数(trunc( )) :**

math()模块是 python 中的标准内置模块。数学( )模块中定义了许多数学函数。要使用 truncate 函数，首先必须导入数学模块，使用 trunc()函数而不定义 math()模块会产生错误。通过使用 math.trunc()函数，可以在 python 中截断一个数字。

## 蟒 3

```
# import math function to use trunc( ) function
import math

num1 = math.trunc(450.63)
print(num1)
print(math.trunc(999998.99999))
print(math.trunc(-89.99))
print(math.trunc(0.99))
```

**输出:**

```
450
999998
-89
0
```

**方法三:使用 split()功能**

split()函数只适用于字符串。因此，使用 str()函数将十进制值转换为字符串，然后在小数点处拆分。执行 split()函数后，这些值仍保留在字符串数据类型中。因此，这些值再次转换为整数数据类型。

## 蟒 3

```
value1 = [998.99, 56.8, 25.6, -52.0]

# values are split at decimal point
lst = []
for each in value1:
    lst.append(str(each).split('.')[0])

# all values converting to integer data type
final_list = [int(i) for i in lst]
print(final_list)
```

**输出:**

```
[998, 56, 25, -52]
```

**注意:**使用 int()函数移除所有十进制值很容易，只需一行代码就可以节省时间。