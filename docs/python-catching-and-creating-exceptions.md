# Python |捕获和创建异常

> 原文:[https://www . geesforgeks . org/python-捕获并创建异常/](https://www.geeksforgeeks.org/python-catching-and-creating-exceptions/)

捕捉所有异常有时被程序员用作拐杖，他们记不住复杂操作中可能出现的所有可能的异常。因此，这也是编写不可出错代码的一个非常好的方法。
正因为如此，如果一个人捕获了所有异常，那么在某个地方记录或报告异常的实际原因(例如，日志文件、打印到屏幕上的错误消息等)是绝对关键的。).

**问题–**捕捉所有异常的代码

**Code #1 : Writing an exception handler for Exception to catch all the exceptions.**

```py
try:
    ...
except Exception as e:
    ...
    # Important 
    log('Reason:', e)
```

这将捕获除`**SystemExit**`、`**KeyboardInterrupt**`和`**GeneratorExit**`以外的所有异常。

**代码#2:考虑示例。**

```py
def parse_int(s):
    try:
        n = int(v)
    except Exception:
        print("Couldn't parse")
```

**代码#3:使用上述功能**

```py
print (parse_int('n / a'), "\n")

print (parse_int('42'))
```

**输出:**

```py
Couldn't parse

Couldn't parse

```

在这一点上，问题出现了，它是如何不起作用的。如果函数被写成:

**代码#4 :**

```py
def parse_int(s):
    try:
        n = int(v)
    except Exception as e:
        print("Couldn't parse")
        print('Reason:', e)
```

在这种情况下，将收到以下输出，这表明出现了编程错误。

```py
parse_int('42')
```

**输出:**

```py
Couldn't parse
Reason: global name 'v' is not defined

```

**问题–**用在应用程序上下文中更有意义的自定义异常包装低级异常(一个正在处理中)。

要创建新的异常，只需将它们定义为从**异常**继承的类(或者其他现有异常类型，如果更有意义的话)。

**代码#5:定义一些自定义异常**

```py
class NetworkError(Exception):
    pass
class HostnameError(NetworkError):
    pass
class TimeoutError(NetworkError):
    pass
class ProtocolError(NetworkError):
    pass
```

**代码#6:以正常方式使用这些异常。**

```py
try:
    msg = s.recv()
except TimeoutError as e:
    ...
except ProtocolError as e:
    ...
```