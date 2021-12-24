# 编码可疑的 Python | C 字符串| Set-1

> 原文:[https://www . geesforgeks . org/python-c-可疑字符串编码-set-1/](https://www.geeksforgeeks.org/python-c-strings-of-doubtful-encoding-set-1/)

可以在 C 和 Python 之间转换字符串，反之亦然，但是 C 编码的性质是可疑的或未知的。让我们假设一个给定的 C 数据应该是 UTF-8，但是它没有被严格执行。因此，处理这种格式错误的数据非常重要，这样它就不会使 Python 崩溃，也不会在这个过程中破坏字符串数据。

**代码#1 : C 数据和说明问题的函数。**

```
/* Some dubious string data (malformed UTF-8) */
const char* sdata = "Spicy Jalape\xc3\xb1o\xae";
int slen = 16;
/* Output character data */
void print_chars(char* s, int len)
{
    int n = 0;
    while (n < len) {
        printf("%2x ", (unsigned char)s[n]);
        n++;
    }
    printf("\n");
}
```

在上面的代码中，字符串 sdata 包含格式错误的数据和 UTF-8 的混合。尽管如此，如果用户在 C 中调用`print_chars(sdata, slen)`，还是可以的。

现在假设想要将 sdata 的内容转换成 Python 字符串，进一步通过扩展将该字符串传递给`print_chars()` 函数。下面给出的代码显示了即使存在编码问题也能准确保留原始数据的方法。

**代码#2 :**

```
/* Return the C string back to Python */
static PyObject *py_retstr(PyObject *self, PyObject *args)
{
    if (!PyArg_ParseTuple(args, ""))
    {
        return NULL;
    }
    return PyUnicode_Decode(sdata, slen, "utf-8", "surrogateescape");
}

/* Wrapper for the print_chars() function */
static PyObject *py_print_chars(PyObject *self, PyObject *args)
{
    PyObject *obj, *bytes;
    char *s = 0;
    Py_ssize_t len;
    if (!PyArg_ParseTuple(args, "U", &obj))
    {
        return NULL;
    }
    if ((bytes = PyUnicode_AsEncodedString(obj,
    "utf-8","surrogateescape"))
            == NULL)
    {
        return NULL;
    }
    PyBytes_AsStringAndSize(bytes, &s, &len);
    print_chars(s, len);
    Py_DECREF(bytes);
    Py_RETURN_NONE;
}
```

**代码#3:使用上面的代码 2**

```
s = retstr()
printf (s)

printf ("\n", print_chars(s))
```

```
'Spicy Jalapeño\udcae'

53 70 69 63 79 20 4a 61 6c 61 70 65 c3 b1 6f ae

```

在这里，可以看到格式错误的字符串被编码成 Python 字符串而没有错误，并且当传递回 C 时，它又变成了与原始 C 字符串编码完全相同字节的字节字符串。