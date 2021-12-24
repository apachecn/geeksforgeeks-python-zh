# Python 中如何将字节转换为字符串？

> 原文:[https://www . geesforgeks . org/如何在 python 中将字节转换为字符串/](https://www.geeksforgeeks.org/how-to-convert-bytes-to-string-in-python/)

数据类型是数据项的分类或归类。它表示一种值，该值告诉可以对特定数据执行哪些操作。因为在 Python 编程中一切都是对象，所以数据类型实际上是类，变量是这些类的实例(对象)。

我们可以使用以下方法将字节转换为字符串:

**方法#1:** 使用 [*解码()*](https://www.geeksforgeeks.org/python-strings-decode-method/) 方法

此方法用于从一种编码方案转换为所需的编码方案，在这种编码方案中，参数字符串被编码。这与编码相反。

## 蟒蛇 3

```
# Program for converting bytes 
# to string using decode()

data = b'GeeksForGeeks'

# display input
print('\nInput:')
print(data)
print(type(data))

# converting
output = data.decode()

# display output
print('\nOutput:')
print(output)
print(type(output))
```

**输出:**

```
Input:
b'GeeksForGeeks'
<class 'bytes'>

Output:
GeeksForGeeks
<class 'str'>
```

**方法 2:** 使用 [*str()*](https://www.geeksforgeeks.org/python-str-function/) 功能

Python 的 *str()* 函数返回对象的字符串版本。

## 蟒蛇 3

```
# Program for converting bytes to string using decode()
data = b'GeeksForGeeks'

# display input
print('\nInput:')
print(data)
print(type(data))

# converting
output = str(data, 'UTF-8')

# display output
print('\nOutput:')
print(output)
print(type(output))
```

**输出:**

```
Input:
b'GeeksForGeeks'
<class 'bytes'>

Output:
GeeksForGeeks
<class 'str'>
```

**方法#3:** 使用[或*编解码器。*方法](https://www.geeksforgeeks.org/codecs-decode-in-python/)

此方法用于将二进制字符串解码为正常形式。

## 蟒蛇 3

```
# Program for converting bytes to string using decode()

# import required module
import codecs

data = b'GeeksForGeeks'

# display input
print('\nInput:')
print(data)
print(type(data))

# converting
output = codecs.decode(data)

# display output
print('\nOutput:')
print(output)
print(type(output))
```

**输出:**

```
Input:
b'GeeksForGeeks'
<class 'bytes'>

Output:
GeeksForGeeks
<class 'str'>
```