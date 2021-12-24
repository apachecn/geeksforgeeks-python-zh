# Python 中如何将分数转换为百分比？

> 原文:[https://www . geesforgeks . org/如何将 python 中的分数转换为百分比/](https://www.geeksforgeeks.org/how-to-convert-fraction-to-percent-in-python/)

分数是整个商品的一部分，可以用分子除以分母的形式来表示。分数的形式为![\pm\frac{p}{q}    ](img/2171c616afd35a9d3cf18e84086ebcc6.png "Rendered by QuickLaTeX.com")，其中 p < =q。

分数和百分比之间有不同的转换方法。

**方法 1:**

分数到百分比的手动转换可以通过将有理数乘以 100 来完成。通过使用内置的 math.round()函数，可以将获得的十进制数向上舍入到所需的位数，该函数具有以下语法:

```py
round(number, digits)
```

## 蟒蛇 3

```py
# define a number
num = 1/3

# converting to decimal value
dec_num = num * 100

# rounding number to required number of decimal places 
print ("Decimal equivalent in %")

# round to 2 places
print (round(dec_num,2))
```

**输出**

```py
Decimal equivalent in %
33.33
```

如果分子能被分母完全整除，这个数就返回到小数点后 1 位。

## 蟒蛇 3

```py
# define a number
num = 2/4

# converting to decimal value
dec_num = num * 100

# rounding number to required number of decimal places 
print ("Decimal equivalent in %")

# round to 2 places
print (round(dec_num,4))
```

**输出**

```py
Decimal equivalent in %
50.0
```

**方法二:**

str.format()方法用于通过指定小数点后的位数将数字转换为百分比。

```py
"{:.n%}".format(num)
```

*   n 代表小数点后的位数
*   num 表示以小数或分数表示的浮点数

分数的分母为 1 的特殊情况，即分数变得等于整数值。

## 蟒蛇 3

```py
# input an integer with denominator =1 
integer_num = 2 
print ("Converting number to percentage rounding to 0 place of decimal")
print ("{:.0%}".format(integer_num))

# input an negative integer with denominator =1 
integer_num = -7 
print ("Converting number to percentage rounding to 5 place of decimal")
print ("{:.5%}".format(integer_num))
```

**输出**

```py
Converting number to percentage rounding to 0 place of decimal

```

## 蟒蛇 3

```py
# input an integer with denominator =1 
integer_num = 2 
print ("Converting number to percentage rounding to 0 place of decimal")
print ("{:.0%}".format(integer_num))

# input an negative integer with denominator =1 
integer_num = -7 
print ("Converting number to percentage rounding to 5 place of decimal")
print ("{:.5%}".format(integer_num))
```

```py
200%
Converting number to percentage rounding to 0 place of decimal
-700.00000%
```

在转换整数时，小数位数不起任何作用，因为数字直接乘以 100。附加到数字上的零的数量相当于所选的小数位数。

下面的 Python 代码用于将有理数转换为等效百分比:

## 蟒蛇 3

```py
# input a fractional number
num = 1/3

# taking 0 places to decimal and convert it to decimal
print ("Converting number to percentage rounding to 0 place of decimal")
print ("{:.0%}".format(num))
num = -2/4

# taking 2 places to decimal and convert it to decimal
print ("Converting number to percentage rounding to 2 place of decimal")
print ("{:.2%}".format(num))
```

**输出**

```py
Converting number to percentage rounding to 0 place of decimal
33%
Converting number to percentage rounding to 2 place of decimal
-50.00%
```