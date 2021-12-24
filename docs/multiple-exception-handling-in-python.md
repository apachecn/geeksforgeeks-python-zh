# Python 中的多重异常处理

> 原文:[https://www . geesforgeks . org/python 中的多重异常处理/](https://www.geeksforgeeks.org/multiple-exception-handling-in-python/)

给定一段可以引发几种不同异常的代码，需要考虑所有可能引发的异常，而不需要创建重复的代码或冗长曲折的代码段。

如果您可以使用单个代码块来处理不同的异常，那么可以将它们组合成一个元组，如下面给出的代码所示:

**代码#1 :**

```
try:
    client_obj.get_url(url)
except (URLError, ValueError, SocketTimeout):
    client_obj.remove_url(url)
```

如果出现任何列出的异常，将调用`remove_url()`方法。另一方面，如果必须以不同的方式处理其中一个异常，则将其放入自己的 except 子句中，如下面给出的代码所示:

**代码#2 :**

```
try:
    client_obj.get_url(url)
except (URLError, ValueError):
    client_obj.remove_url(url)
except SocketTimeout:
    client_obj.handle_url_timeout(url)
```

许多异常被归入一个继承层次结构。对于这样的异常，只需指定一个基类就可以捕获所有的异常。例如，不像下面给出的代码那样编写代码–

**代码#3 :**

```
try:
    f = open(filename)
except (FileNotFoundError, PermissionError):
    ...
```

除非语句可以按照下面给出的代码重写。这是可行的，因为`OSError`是一个基类，对于`FileNotFoundError`和**权限错误**异常是通用的。

**代码#4 :**

```
try:
    f = open(filename)
except OSError:
    ...
```

虽然根据 **se** 处理多个异常并不具体，但值得注意的是，可以使用它们作为关键字来处理抛出的异常，如下面给出的代码所示。

**代码#5 :**

```
try:
    f = open(filename)

except OSError as e:
    if e.errno == errno.ENOENT:
        logger.error('File not found')
    elif e.errno == errno.EACCES:
        logger.error('Permission denied')
    else:
        logger.error('Unexpected error: % d', e.errno)
```

**e** 变量保存了一个引发的 OSError 的实例。如果必须对异常进行进一步的投资，例如根据附加状态代码的值对其进行处理，这将非常有用。将按照列出的顺序检查 except 子句，并执行第一个匹配。

**代码#6:创建多个除子句可能匹配**

```
f = open('missing')
```

的情况

**输出:**

```
Traceback (most recent call last):
File "", line 1, in 
FileNotFoundError: [Errno 2] No such file or directory: 'miss

```

```
try:
    f = open('missing')
    except OSError:
        print('It failed')
    except FileNotFoundError:
        print('File not found')
```

**输出:**

```
Failed

```

这里除了`FileNotFoundError` 子句不执行，因为`OSError`更一般，匹配 FileNotFoundError 异常，并且被列在第一位。