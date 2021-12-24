# 处理 Python 中的名称错误异常

> 原文:[https://www . geesforgeks . org/handling-name error-exception-in-python/](https://www.geeksforgeeks.org/handling-nameerror-exception-in-python/)

**先决条件:** [Python 异常处理](https://www.geeksforgeeks.org/python-exception-handling/)

Python 中有几个标准的例外，NameError 就是其中之一。**名称错误**在被访问的标识符未在本地或全局范围内定义时引发。引发名称错误的一般原因是:

**1。拼写错误的内置函数:**

在下面的示例代码中，print 语句拼错了，因此将引发 NameError。

## 蟒蛇 3

```py
geek = input()
prit(geek)
```

**输出:**

```py
NameError: name 'prit' is not defined
```

**2。使用未定义的变量:**

当下面的程序被执行时，由于变量 geek 从未被定义，将会引发 NameError。

## 蟒蛇 3

```py
geeky = input()
print(geek)
```

**输出:**

```py
NameError: name 'geek' is not defined
```

**3。使用后定义变量:**

在下面的例子中，即使变量 geek 是在程序中定义的，它也是在使用之后定义的。由于 Python 从上到下解释代码，这将引发名称错误

## 蟒蛇 3

```py
print(geek)
geek = "GeeksforGeeks"
```

**输出:**

```py
NameError: name 'geek' is not defined
```

**4。范围使用不正确:**

在下面的示例程序中，变量 geek 是在赋值函数的局部范围内定义的。因此，它不能被全局访问。这会引发名称错误。

## 蟒蛇 3

```py
def assign():
    geek = "GeeksforGeeks"

assign()
print(geek)
```

**输出:**

```py
NameError: name 'geek' is not defined
```

### 处理名称错误

要在 Python 中专门处理名称错误，您需要在 except 语句中提到它。在下面的代码示例中，如果在 try 块中只引发了 NameError，那么控制台上将会显示一条错误消息。

## 蟒蛇 3

```py
def geek_message():
    try:
        geek = "GeeksforGeeks"
        return geeksforgeeks
    except NameError:
        return "NameError occurred. Some variable isn't defined."

print(geek_message())
```

**输出:**

```py
NameError occurred. Some variable isn't defined.
```