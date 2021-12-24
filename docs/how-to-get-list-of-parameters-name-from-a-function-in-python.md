# 如何在 Python 中从函数中获取参数名称列表？

> 原文:[https://www . geesforgeks . org/如何从 python 函数中获取参数列表名称/](https://www.geeksforgeeks.org/how-to-get-list-of-parameters-name-from-a-function-in-python/)

在本文中，我们将讨论如何从 Python 中的函数获取列表参数。[*检查*](https://www.geeksforgeeks.org/inspect-module-in-python/) 模块有助于检查我们编写的代码中存在的对象。我们将使用两种方法，即 *inspect* 模块中的 *signature()* 和 *getargspec()* 方法，以获取在其中一种方法中作为参数传递的函数或方法的参数名称列表。

### 使用*检查签名()*方法

下面是一些程序，描述了如何使用 *检查*模块的*签名()*方法来获取参数名称列表:

**例 1:** 获取某方法的参数表。

## 蟒蛇 3

```
# import required modules
import inspect
import collections

# use signature()
print(inspect.signature(collections.Counter))
```

**输出:**

```
(*args, **kwds)
```

**示例 2:** 获取显式函数的参数列表。

## 蟒蛇 3

```
# explicit function
def fun(a, b):
    return a**b

# import required modules 
import inspect 

# use signature() 
print(inspect.signature(fun)) 
```

**输出:**

```
(a, b)
```

**例 3:** 获取内置函数的参数表。

## 蟒蛇 3

```
# import required modules 
import inspect 

# use signature() 
print(inspect.signature(len))
```

**输出:**

```
(obj, /)
```

### 使用*检查*方法

下面是一些程序，描述了如何使用 *检查*模块的 *getargspec()* 方法来获取参数名称列表:

**例 1:** 获取某方法的参数表。

## 蟒蛇 3

```
# import required modules
import inspect
import collections

# use getargspec()
print(inspect.getargspec(collections.Counter))
```

**输出:**

> ArgSpec(args=[]，varargs='args '，关键字='kwds '，默认值=无)

**示例 2:** 获取显式函数的参数列表。

## 蟒蛇 3

```
# explicit function
def fun(a, b):
    return a**b

# import required modules 
import inspect 

# use getargspec() 
print(inspect.getargspec(fun)) 
```

**输出:**

> ArgSpec(args=['a '，' b']，varargs =无，关键字=无，默认值=无)

**例 3:** 获取内置函数的参数表。

## 蟒蛇 3

```
# import required modules 
import inspect 

# use getargspec() 
print(inspect.getargspec(len))
```

**输出:**

> ArgSpec(args=['obj']，varargs =无，关键字=无，默认值=无)