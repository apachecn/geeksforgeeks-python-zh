# Python |在数组上运行的扩展功能

> 原文:[https://www . geesforgeks . org/python-extension-function-operating-on-arrays/](https://www.geeksforgeeks.org/python-extension-function-operating-on-arrays/)

让我们编写一个 C 扩展函数，它可以对连续的数据数组进行操作，这可能是由数组模块或像 NumPy 这样的库创建的，并且这个函数应该是通用的，而不是特定于任何一个数组库的。

代码应该使用缓冲协议以可移植的方式接收和处理数组。下面的代码是一个 C 扩展函数，它接收数组数据，并使用 Python 中的 C 代码调用本文中的`**avg(double *buf, int len)**`函数–。

**代码#1 :**

```py
/* Call double avg(double *, int) */
static PyObject *py_avg(PyObject *self, PyObject *args)
{
    PyObject *bufobj;
    Py_buffer view;
    double result;
    /* Get the passed Python object */
    if (!PyArg_ParseTuple(args, "O", &bufobj))
    {
        return NULL;
    }

    /* Attempt to extract buffer information from it */

    if (PyObject_GetBuffer(bufobj, &view,
                           PyBUF_ANY_CONTIGUOUS | PyBUF_FORMAT) == -1)
    {
        return NULL;
    }

    if (view.ndim != 1)
    {
        PyErr_SetString(PyExc_TypeError, "Expected a 1-dimensional array");
        PyBuffer_Release(&view);
        return NULL;
    }

    /* Check the type of items in the array */
    if (strcmp(view.format, "d") != 0)
    {
        PyErr_SetString(PyExc_TypeError, "Expected an array of doubles");
        PyBuffer_Release(&view);
        return NULL;
    }

    /* Pass the raw buffer and size to the C function */
    result = avg(view.buf, view.shape[0]);

    /* Indicate we're done working with the buffer */
    PyBuffer_Release(&view);
    return Py_BuildValue("d", result);
}
```

**代码#2:这个扩展功能是如何工作的**

```py
import array

print("Average : ", avg(array.array('d', [1, 2, 3])))

import numpy
print("Average numpy array : ", avg(numpy.array([1.0, 2.0, 3.0])))
print ("Average list : \n", avg([1, 2, 3]))
```

**输出:**

```py
Average : 2.0

Average numpy array : 2.0
```

```py
Average list : 
Traceback (most recent call last):
File "", line 1, in 
TypeError: 'list' does not support the buffer interface

```

*   **`PyBuffer_GetBuffer()`** 功能是文章中代码的关键。
*   它试图在给定的任意 Python 对象中获取关于内存表示的信息。
*   如果无法获得信息(就像普通 Python 对象一样)，它只会引发异常并返回-1。
*   传递给 **`PyBuffer_GetBuffer()`** 的特殊标志给出了关于所请求的内存缓冲类型的额外提示。
*   As，***PyBUF _ ANY _ contact***指定需要一个连续的内存区域。