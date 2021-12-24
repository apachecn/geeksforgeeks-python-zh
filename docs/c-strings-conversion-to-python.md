# C 字符串转换为 Python

> 原文:[https://www . geesforgeks . org/c-strings-conversion-to-python/](https://www.geeksforgeeks.org/c-strings-conversion-to-python/)

对于表示为一对 **`char *, int`** 的 C 字符串，要决定是否将该字符串表示为原始字节字符串或 Unicode 字符串。

字节对象可以使用`**Py_BuildValue()**`作为

```
// Pointer to C string data
char *s; 

// Length of data 
int len; 

// Make a bytes object
PyObject *obj = Py_BuildValue("y#", s, len);
```

要创建 Unicode 字符串，并且已知 s 指向编码为 UTF-8 的数据，下面给出的代码可以用作–

```
PyObject *obj = Py_BuildValue("s#", s, len);
```

如果*的*是以其他已知的编码方式编码的，则使用`**PyUnicode_Decode()**`的字符串可以表示为:

```
PyObject *obj = PyUnicode_Decode(s, len, "encoding", "errors");

// Example
obj = PyUnicode_Decode(s, len, "latin-1", "strict");
obj = PyUnicode_Decode(s, len, "ascii", "ignore");
```

如果需要将宽字符串表示为`wchar_t *, len`对。下面是几个选项–

```
// Wide character string
wchar_t *w;

// Length
int len; 

// Option 1 - use Py_BuildValue()
PyObject *obj = Py_BuildValue("u#", w, len);

// Option 2 - use PyUnicode_FromWideChar()
PyObject *obj = PyUnicode_FromWideChar(w, len);
```

*   来自 C 的数据必须根据某种编解码器显式解码成字符串
*   常见的编码包括 ASCII、拉丁文-1 和 UTF-8。
*   如果您的编码未知，那么最好将字符串编码为字节。
*   Python 在创建对象时总是复制字符串数据(正在提供)。
*   此外，为了更好的可靠性，应该使用指针和大小来创建字符串，而不是依赖以空终止的数据。