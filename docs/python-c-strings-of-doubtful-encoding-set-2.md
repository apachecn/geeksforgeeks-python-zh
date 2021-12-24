# 编码可疑的 Python | C 字符串| Set-2

> 原文:[https://www . geesforgeks . org/python-c-可疑字符串编码-set-2/](https://www.geeksforgeeks.org/python-c-strings-of-doubtful-encoding-set-2/)

扩展模块中的字符串处理是一个问题。扩展中的 c 字符串可能不遵循 Python 通常期望的严格的 Unicode 编码/解码规则。因此，一些格式错误的 C 数据可能会传递给 Python。一个很好的例子可能是与低级系统调用(如文件名)相关联的 C 字符串。例如，如果系统调用向解释器返回一个无法正确解码的断串，会发生什么。

通常，Unicode 错误通常通过指定某种错误策略来处理，例如严格、忽略、替换或类似的策略。然而，这些策略的缺点是它们不可修复地破坏了原始字符串内容。
例如，如果使用这些策略之一对示例中的格式错误的数据进行解码，您将获得如下所示的结果–

**代码#1 :**

```py
raw = b'Spicy Jalape\xc3\xb1o\xae'

print (raw.decode('utf-8', 'ignore'))

print (raw.decode('utf-8', 'replace'))
```

**输出:**

```py
'Spicy Jalapeño'
'Spicy Jalapeño?'
```

*代理技术场景*错误处理策略获取所有不可编码的字节，并将它们转换为代理对的下半部分(其中 XX 是原始字节值)。

**代码#2 :**

```py
print (raw.decode('utf-8', 'surrogateescape'))
```

**输出:**

```py
'Spicy Jalapeño\udcae'
```

孤立的低代理字符(如\udcae)永远不会出现在有效的 Unicode 中。因此，这个字符串在技术上是非法的表示。事实上，如果试图将它传递给执行输出的函数，就会出现编码错误。

**代码#3 :**

```py
s = raw.decode('utf-8', 'surrogateescape')
print(s)
```

**输出:**

```py
Traceback (most recent call last):
File "", line 1, in 
UnicodeEncodeError: 'utf-8' codec can't encode 
character '\udcae' in position 14: surrogates not allowed
```

然而，允许代理转义的主要目的是允许格式错误的字符串从 C 语言传递到 Python 语言并返回到 C 语言，而不会丢失任何数据。当再次使用替代技术对字符串进行编码时，替代字符将变回其原始字节。例如:

**代码#4:**

```py
print (s)
print(s.encode('utf-8', 'surrogateescape'))
```

**输出:**

```py
'Spicy Jalapeño\udcae'
b'Spicy Jalape\xc3\xb1o\xae'
```

一般来说，最好尽可能避免代理编码。如果使用正确的编码，代码将更加可靠。然而，有时会出现这样的情况，人们根本无法控制数据编码，也无法随意忽略或替换坏数据，因为其他函数可能需要使用它。

最后，Python 的许多面向系统的函数，尤其是那些与文件名、环境变量和命令行选项相关的函数，都使用代理编码。例如，如果在包含不可解码文件名的目录中使用了像`os.listdir()`这样的函数，它将作为带有代理转义的字符串返回。