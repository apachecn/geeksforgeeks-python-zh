# Python 字符串中%s 和%d 的区别

> 原文:[https://www . geesforgeks . org/python 字符串中 s 和 d 的区别/](https://www.geeksforgeeks.org/difference-between-s-and-d-in-python-string/)

在本文中，我们将看到 Python 中%s 和%d 的区别。在这里，我们从一次正确解释一个开始，然后两个都解释，最后比较它们。

## **%s 操作员**

%符号在 Python 中用于各种数据类型和配置。它用作参数说明符和字符串格式化程序。%s 专门用于将字符串连接在一起。它允许我们格式化字符串中的值。它用于在字符串中包含另一个字符串。它自动提供从值到字符串的类型转换。

%s 运算符放在要指定字符串的位置。要追加到字符串中的值的数量应该等于字符串值末尾的%运算符后括号中指定的数量。以下代码说明了%s 符号的用法:

## 蟒蛇 3

```
# declaring a string variable
name = "Geek"
#append a string within a string 
print("Hey, %s!" % name)
```

**输出**

```
Hey, Geek!
```

## **%d 操作员**

%d 运算符用作占位符来指定整数值、小数或数字。它允许我们打印字符串或其他值中的数字。%d 运算符放在要指定整数的位置。浮点数会自动转换为十进制值。

## 蟒蛇 3

```
#declaring numeric variables
num = 2021
#concatenating numeric value within string
print("%d is here!!" % num)
```

**输出**

```
2021 is here!!
```

小数和有理数四舍五入到绝对整数部分，小数点后的数字刮掉，也就是只提取整数。下面的代码说明了%d 在十进制和小数中的用法:

## 蟒蛇 3

```
#declaring rational number
frac_num = 8/3
#concatenating numeric value within string
print ("Rational number formatting using %d")
print("%d is equal to 8/3 using this operator." % frac_num)

#declaring decimal number
dec_num = 10.9785
#concatenating numeric value within string
print ("Decimal number formatting using %d")
print("%d is equal to 10.9785 using this operator." % dec_num)
```

**输出**

```
Rational number formatting using %d
2 is equal to 8/3 using this operator.
Decimal number formatting using %d
10 is equal to 10.9785 using this operator.
```

## %s 和%d 运算符

我们也可以在单个程序中使用运算符的组合。在此之前，首先通过比较明确一些概念，如下所示:

<figure class="table">

| **%s** | **%d** |
| --- | --- |
| 它用作字符串值的占位符。 | 它用作数值的占位符。 |
| 格式化前通过 str()使用字符串转换。 | 格式化前通过 int()使用十进制转换。 |
| %s 也可以接受数值，它会自动进行类型转换。 | 如果为%d 运算符指定了字符串，则会返回类型错误。 |

</figure>

## 蟒蛇 3

```
name = "Sita"
age = 22
print("Using %s and %d both")
print ("%s's age is %d."%(name,age))
```

**输出**

```
Using %s and %d both
Sita's age is 22.
```

**注 1:** %s 自动将数值转换为字符串，不会引发错误。

## 蟒蛇 3

```
name = "Sita"
age = 22
print("Using %s ")
print ("%s's age is %s."%(name,age))
```

**输出**

```
Using %s 
Sita's age is 22.
```

**注 2:** %d 不过，只能用于数值。否则，将返回一个错误。

## 蟒蛇 3

```
name = "Sita"
age = 22
print("Using %d")
print ("%d's age is %d."%(name,age))
```

**错误**

```
Using %d
Traceback (most recent call last):
 File "<string>", line 4, in <module>
TypeError: %d format: a number is required, not str
```