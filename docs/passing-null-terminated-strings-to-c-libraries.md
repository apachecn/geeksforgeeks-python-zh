# 将空终止字符串传递给 C 库

> 原文:[https://www . geesforgeks . org/passing-null-ended-strings-to-c-libraries/](https://www.geeksforgeeks.org/passing-null-terminated-strings-to-c-libraries/)

如果你想要一个扩展模块，它需要传递一个空终止的字符串到一个 C 库。让我们看看如何使用 Python 的 Unicode 字符串实现来实现它。c 函数库有很多函数对声明为`**type char ***`的空终止字符串进行操作。

下面给出的代码有一个 C 函数，我们将演示和测试这个问题。C 函数(*代码#1* )只需打印单个字符的十六进制表示，这样就可以轻松调试传递的字符串。

**代码#1 :**

```
void print_chars(char *s)
{
    while (*s)
    {
        printf("%2x ", (unsigned char) *s);
        s++;
    }
    printf("\n");
}

print_chars("Hello");
```

**输出:**

```
48 65 6c 6c 6f

```

从 Python 调用这样的 C 函数，选择很少。首先是–可以限制为只对字节进行操作，使用“y”转换代码到`**PyArg_ParseTuple()**`，如下图代码所示。

**代码#2 :**

```
static PyObject * py_print_chars(PyObject * self, PyObject * args)
{
    char * s;
    if (! PyArg_ParseTuple(args, "y", &s))
    {
        return NULL;
    }
    print_chars(s);
    Py_RETURN_NONE;
}
```

我们来看看 to 结果函数是如何运行的，以及嵌入了 NULL 字节和 Unicode 字符串的字节是如何被拒绝的。

**代码#3 :**

```
print (print_chars(b'Hello World'))

print ("\n", print_chars(b'Hello\x00World'))

print ("\n", print_chars('Hello World'))
```

**输出:**

```
48 65 6c 6c 6f 20 57 6f 72 6c 64

Traceback (most recent call last):
File "", line 1, in 
TypeError: must be bytes without null bytes, not bytes

Traceback (most recent call last):
File "", line 1, in 
TypeError: 'str' does not support the buffer interface

```

如果要改为传递 Unicode 字符串，请使用“s”格式代码到`**PyArg_ParseTuple()**`，如下所示。

**代码#4 :**

```
static PyObject *py_print_chars(PyObject *self, PyObject *args)
{
    char *s;
    if (!PyArg_ParseTuple(args, "s", &s))
    {
        return NULL;
    }
    print_chars(s);
    Py_RETURN_NONE;
}
```

使用上述代码(*代码#4* )将自动将所有字符串转换为以 NULL 结尾的 UTF-8 编码。如下代码所示。

**代码#5 :**

```
print (print_chars('Hello World'))

# UTF-8 encoding
print ("\n", print_chars('Spicy Jalape\u00f1o'))

print ("\n", print_chars('Hello\x00World'))

print ("\n", print_chars(b'Hello World'))
```

**输出:**

```
48 65 6c 6c 6f 20 57 6f 72 6c 64

53 70 69 63 79 20 4a 61 6c 61 70 65 c3 b1 6f

Traceback (most recent call last):
File "", line 1, in 
TypeError: must be str without null characters, not str

Traceback (most recent call last):
File "", line 1, in 
TypeError: must be str, not bytes

```

如果使用`**PyObject ***`并且不能使用`PyArg_ParseTuple()`，下面的代码解释了如何从字节和字符串对象中检查和提取合适的`char *`引用。

**代码#6:字节转换**

```
// Some Python Object
PyObject *obj;

// Conversion from bytes 
{
    char *s;
    s = PyBytes_AsString(o);
    if (!s)
    {
        /* TypeError already raised */
        return NULL; 
    }
    print_chars(s);
}
```

**代码#7:从字符串转换到 UTF-8 字节**

```
{

    PyObject *bytes;
    char *s;

    if (!PyUnicode_Check(obj))
    {
        PyErr_SetString(PyExc_TypeError, "Expected string");
        return NULL;
    }

    bytes = PyUnicode_AsUTF8String(obj);
    s = PyBytes_AsString(bytes);
    print_chars(s);
    Py_DECREF(bytes);
}
```

这两种代码转换都保证了以空值结尾的数据，但是没有检查字符串中其他地方嵌入的空字节。如果这很重要的话，需要检查一下。

**注意:**使用“s”格式代码到`**PyArg_ParseTuple()**`有一个隐藏的内存开销，很容易被忽略。当编写使用这种转换的代码时，会创建一个 UTF-8 字符串，并将其永久附加到原始字符串对象上，如果原始字符串对象包含非 ASCII 字符，则该字符串的大小会增加，直到被垃圾收集。

**代码#8 :**

```
import sys
s = 'Spicy Jalape\u00f1o'
print ("Size : ", sys.getsizeof(s))

# passing string
print("\n", print_chars(s))

# increasing size
print ("\nSize : ", sys.getsizeof(s))
```

**输出:**

```
Size : 87

53 70 69 63 79 20 4a 61 6c 61 70 65 c3 b1 6f

Size : 103

```