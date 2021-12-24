# 在 Python 中将科学符号显示为浮点数

> 原文:[https://www . geesforgeks . org/display-scientific-notification-as-float-in-python/](https://www.geeksforgeeks.org/display-scientific-notation-as-float-in-python/)

在本文中，任务是在 Python 中将科学符号显示为 [float](https://www.geeksforgeeks.org/python-float-type-and-its-methods/) 。科学记数法是指任何以 10 的幂表示的数字，例如- 340 可以用科学记数法写成 3.4 X10 <sup>2</sup> 。在蟒蛇中，我们对带有“{:e}”的数字使用 [str.format()](https://www.geeksforgeeks.org/python-format-function/) 将数字格式化为科学符号。str.format()将数字格式化为浮点数，后跟“e+”和适当的 10 次方。例如- 340 将显示为 3.4e+2

**示例:**

> -51000000000.0000000 在科学记数法中的结果为“5.10e+10”，其中“e+”后的数字表示 10 的幂
> -5189 在科学记数法中的结果为“5.189 e+3”
> -439929 在科学记数法中的结果为“4.39929e+5”

## 蟒蛇 3

```py
# code
scientific_format = "{:e}".format(512349000.000000)

print(scientific_format)
```

**输出:**

```py
5.123490e+08
```

在上面的例子中，512349000.000000 的科学符号将是第一个数字和 10 的幂 ie- 5.123490 X 108 之后的十进制数

为了在小数点后只包含一定数量的数字，我们使用“{:”。Ne}”，其中 N 为位数。

## 蟒蛇 3

```py
# code
# code
# after decimal point,only 3 digit will be displayed
print("{:.3e}".format(345000))
```

**输出:**

```py
3.450e+05
```

显示科学数字的反序

我们必须传递一个保存数字的科学格式的变量，如下所示:

## 蟒蛇 3

```py
# code
x = 3.234e+4

print("{:f}".format(x))  # f represents float
```

**输出:**

```py
32340.000000
```