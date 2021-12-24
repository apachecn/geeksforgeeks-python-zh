# Python: AttributeError

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-attribute error/

在每种编程语言中，如果我们开发新程序，很有可能会出现错误或异常。这些错误导致程序无法执行。Python 中最常出现的错误之一是“属性错误”。属性错误可以定义为属性引用或赋值失败时引发的错误。
例如，如果我们取一个变量 x，我们被赋予一个值 10。在这个过程中，假设我们想给变量附加另一个值。这不可能。因为变量是整数类型，所以它不支持 append 方法。所以在这类问题中，我们会得到一个名为“属性错误”的错误。假设变量是列表类型，那么它支持 append 方法。那么就没有问题，不会得到“属性错误”。

**注意:**Python 中的属性错误一般是在进行无效属性引用时引发的。
出现属性错误的可能性很小。

**例 1:**

## 蟒蛇 3

```
# Python program to demonstrate
# AttributeError

X = 10

# Raises an AttributeError
X.append(6)
```

**输出:**

```
Traceback (most recent call last):
  File "/home/46576cfdd7cb1db75480a8653e2115cc.py", line 5, in 
    X.append(6)
AttributeError: 'int' object has no attribute 'append'
```

**示例 2:** 由于 Python 是一种区分大小写的语言，因此有时拼写的任何变化都会导致属性错误。

## 蟒蛇 3

```
# Python program to demonstrate
# AttributeError

# Raises an AttributeError as there is no
# method as fst for strings
string = "The famous website is { }".fst("geeksforgeeks")
print(string)
```

**输出:**

```
Traceback (most recent call last):
  File "/home/2078367df38257e2ec3aead22841c153.py", line 3, in 
    string = "The famous website is { }".fst("geeksforgeeks")
AttributeError: 'str' object has no attribute 'fst'
```

**示例 3:** 当用户试图进行无效的属性引用时，用户定义的类也会出现属性错误。

## 蟒蛇 3

```
# Python program to demonstrate
# AttributeError

class Geeks():

    def __init__(self):
        self.a = 'GeeksforGeeks'

# Driver's code
obj = Geeks()

print(obj.a)

# Raises an AttributeError as there
# is no attribute b
print(obj.b)
```

**输出:**

```
GeeksforGeeks
```

**错误:**

```
Traceback (most recent call last):
  File "/home/373989a62f52a8b91cb2d3300f411083.py", line 17, in 
    print(obj.b)
AttributeError: 'Geeks' object has no attribute 'b'
```

### **属性错误的解决方案**

Python 中的错误和异常可以使用[异常处理](https://www.geeksforgeeks.org/python-set-5-exception-handling/)来处理，即使用 Python 中的[try and exception](https://www.geeksforgeeks.org/try-except-python/)。

**示例:**考虑上面的类示例，我们希望做一些其他的事情，而不是每当引发属性错误时就打印回溯。

## 蟒蛇 3

```
# Python program to demonstrate
# AttributeError

class Geeks():

    def __init__(self):
        self.a = 'GeeksforGeeks'

# Driver's code
obj = Geeks()

# Try and except statement for
# Exception handling
try:
    print(obj.a)

    # Raises an AttributeError
    print(obj.b)

# Prints the below statement
# whenever an AttributeError is
# raised
except AttributeError:
    print("There is no such attribute")
```

**输出:**

```
GeeksforGeeks
There is no such attribute
```

**注意:**想了解更多[异常处理](https://www.geeksforgeeks.org/python-set-5-exception-handling/)点击这里。