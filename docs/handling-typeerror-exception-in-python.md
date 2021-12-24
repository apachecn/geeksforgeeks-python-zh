# 在 Python 中处理类型错误异常

> 原文:[https://www . geesforgeks . org/handling-type error-exception-in-python/](https://www.geeksforgeeks.org/handling-typeerror-exception-in-python/)

类型错误是几个标准 Python 异常之一。**每当对不正确/不支持的对象类型执行操作时，都会引发类型错误**。例如，对字符串和整数值使用+(加法)运算符将引发类型错误。

#### 例子

引发类型错误的一般原因是:

**1。两种类型之间不支持的操作:**

在下面的例子中，变量“geek”是一个字符串，变量“num”是一个整数。+(加法)运算符不能在这两种类型之间使用，因此会引发类型错误。

## 蟒蛇 3

```py
geek = "Geeks"
num = 4
print(geek + num + geek)
```

**输出:**

```py
TypeError: must be str, not int

```

**2。调用不可调用的标识符:**

在下面的示例代码中，变量“geek”是一个字符串，在这种情况下是不可调用的。因为它是在 print 语句中调用的，所以会引发 TypeError。

## 蟒蛇 3

```py
geek = "GeeksforGeeks"
print(geek())
```

**输出:**

```py
TypeError: 'str' object is not callable

```

**3。列表索引类型不正确:**

在 Python 中，列表索引必须始终是整数值。由于以下代码中使用的索引值是字符串，因此会引发类型错误。

## 蟒蛇 3

```py
geeky_list = ["geek", "GeeksforGeeks", "geeky", "geekgod"]
index = "1"
print(geeky_list[index])
```

**输出:**

```py
TypeError: list indices must be integers or slices, not str

```

**4。迭代通过非迭代标识符:**

在下面的代码中，值 1234.567890 是一个浮点数，因此它是非迭代的。强制 Python 迭代非迭代标识符将引发类型错误。

## 蟒蛇 3

```py
for geek in 1234.567890:
    print(geek)
```

**输出:**

```py
TypeError: 'float' object is not iterable

```

### 恐怖行动

类型错误主要出现在程序员在对对象执行操作之前未能检查对象类型的情况下。可以通过在 except 块中提到它们来具体处理它们。在下面的示例中，当发现其中一个索引是不正确的类型时，程序会引发并处理异常。

## 蟒蛇 3

```py
geeky_list = ["Geeky", "GeeksforGeeks", "SuperGeek", "Geek"]
indices = [0, 1, "2", 3]
for i in range(len(indices)):
    try:
        print(geeky_list[indices[i]])
    except TypeError:
        print("TypeError: Check list of indices")
```

**输出:**

```py
Geeky
GeeksforGeeks
TypeError: Check list of indices
Geek

```