# 在 Python 中将集合转换为字符串

> 原文:[https://www . geesforgeks . org/convert-set-to-string-in-python/](https://www.geeksforgeeks.org/convert-set-to-string-in-python/)

在本文中，我们将讨论如何在 Python 中将集合转换为字符串。这可以通过两种方式实现–

**方法 1:** 使用[str()](https://www.geeksforgeeks.org/python-str-function/)T4【我们将使用 [str()](https://www.geeksforgeeks.org/python-str-function/) 函数将 Python 中的集合转换为字符串。

> **语法:** str(对象，编码= 'utf-8？，错误= '严格')
> 
> **参数:**
> 
> *   **对象:**要返回字符串表示的对象。
> *   **编码:**给定对象的编码。
> *   **错误:**解码失败时的响应。
> 
> **返回:**给定对象的字符串版本

**例 1 :**

```py
# create a set
s = {'a', 'b', 'c', 'd'}
print("Initially")
print("The datatype of s : " + str(type(s)))
print("Contents of s : ", s)

# convert Set to String
s = str(s)
print("\nAfter the conversion")
print("The datatype of s : " + str(type(s)))
print("Contents of s : " + s)
```

**输出:**

```py
Initially
The datatype of s : <class 'set'>
Contents of s :  {'c', 'd', 'a', 'b'}

After the conversion
The datatype of s : <class 'str'>
Contents of s : {'c', 'd', 'a', 'b'}

```

**例 2 :**

```py
# create a set
s = {'g', 'e', 'e', 'k', 's'}
print("Initially")
print("The datatype of s : " + str(type(s)))
print("Contents of s : ", s)

# convert Set to String
s = str(s)
print("\nAfter the conversion")
print("The datatype of s : " + str(type(s)))
print("Contents of s : " + s)
```

**输出:**

```py
Initially
The datatype of s : <class 'set'>
Contents of s :  {'k', 'g', 's', 'e'}

After the conversion
The datatype of s : <class 'str'>
Contents of s : {'k', 'g', 's', 'e'}

```

**方法二:**使用[连接()](https://www.geeksforgeeks.org/join-function-python/)

join()方法是一个字符串方法，它返回一个字符串，在该字符串中，序列的元素通过字符串分隔符连接在一起。

**语法:**

```py
string_name.join(iterable) 
```

```py
# create a set
s = {'a', 'b', 'c', 'd'}
print("Initially")
print("The datatype of s : " + str(type(s)))
print("Contents of s : ", s)

# convert Set to String
S = ', '.join(s)
print("The datatype of s : " + str(type(S)))
print("Contents of s : ", S)
```

**输出:**

```py
Initially
The datatype of s : <class 'set'>
Contents of s :  {'c', 'd', 'a', 'b'}
The datatype of s : <class 'str'>
Contents of s :  c, d, a, b
```