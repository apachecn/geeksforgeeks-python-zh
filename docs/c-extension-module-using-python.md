# 使用 Python 的 C 扩展模块

> 原文:[https://www . geesforgeks . org/c-extension-module-use-python/](https://www.geeksforgeeks.org/c-extension-module-using-python/)

直接使用 Python 的扩展 API 编写一个简单的 C 扩展模块，不需要其他工具。为一个简单的 C 代码制作一个手工的扩展模块是很简单的。但是首先，我们必须确保 C 代码有一个合适的头文件。

**代码#1 :**

```py
#include <math.h>

extern int gcd(int, int);
extern int in_mandel(double x0, double y0, int n);
extern int divide(int a, int b, int *remainder);
extern double avg(double *a, int n);

typedef struct Point
{
    double x, y;
} Point;

extern double distance(Point *p1, Point *p2);
```

标题将对应于已经单独编译的库。遵循这个假设，下面的代码说明了编写扩展函数的基础。

**代码#2:**

```py
# include "Python.h"
# include "sample.h"

/* int gcd(int, int) */
static PyObject * py_gcd(PyObject * self, PyObject * args)
{
    int x, y, result;
    if (! PyArg_ParseTuple(args, "ii", &x, &y))
    {
        return NULL;
    }
    result = gcd(x, y);
    return Py_BuildValue("i", result);
}

/* int divide(int, int, int *) */
static PyObject * py_divide(PyObject * self, PyObject * args)
{
    int a, b, quotient, remainder;
    if (! PyArg_ParseTuple(args, "ii", &a, &b))
    {
        return NULL;
    }
    quotient = divide(a, b, &remainder);
    return Py_BuildValue("(ii)", quotient, remainder);
}
```

**代码#3:模块方法表及结构**

```py
/* Module method table */
static PyMethodDef SampleMethods[] =
{
    {"gcd", py_gcd, METH_VARARGS, "Greatest common divisor"},
    {"divide", py_divide, METH_VARARGS, "Integer division"},
    { NULL, NULL, 0, NULL}
};

/* Module structure */
static struct PyModuleDef samplemodule =
{
    PyModuleDef_HEAD_INIT,
    "sample", /* name of module */
    "A sample module", /* Doc string (may be NULL) */
    -1, /* Size of per-interpreter state or -1 */
    SampleMethods /* Method table */
};

/* Module initialization function */
PyMODINIT_FUNC
PyInit_sample(void)
{
    return PyModule_Create(&samplemodule);
}
```

**代码#4:** **创建一个`**setup.py**` python 文件来构建扩展模块。**

```py
# setup.py
from distutils.core import setup, Extension

setup(name='sample',
    ext_modules=[
            Extension('sample',
                    ['pysample.c'],
                    include_dirs = ['/some/dir'],
                    define_macros = [('FOO','1')],
                    undef_macros = ['BAR'],
                    library_dirs = ['/usr/local/lib'],
                    libraries = ['sample']
                    )
            ]
)
```

**代码#5:** 现在只需使用 python3 *buildlib.py* `build_ext --inplace`，构建结果库。

```py
bash% python3 setup.py build_ext --inplace
running build_ext
building 'sample' extension
gcc -fno-strict-aliasing -DNDEBUG -g -fwrapv -O3 -Wall -Wstrict-prototypes
  -I/usr/local/include/python3.3m -c pysample.c
  -o build/temp.macosx-10.6-x86_64-3.3/pysample.o
gcc -bundle -undefined dynamic_lookup
build/temp.macosx-10.6-x86_64-3.3/pysample.o \
  -L/usr/local/lib -lsample -o sample.so
bash %

```

上面的代码将创建一个名为**示例的共享库。

**代码#6 :****

```py
import sample

print ("gcd = ", sample.gcd(35, 42))

print ("\ndistance : ", sample.divide(42, 8))
```

**输出:**

```py
gcd = 7

distance = (5, 2)

```

**[扩展和嵌入 Python 解释器](https://docs.python.org/3/extending/)**是一个 Python 文档，在尝试任何手写扩展之前都可以查阅。

在扩展模块中，函数可以如下面的代码片段所示编写。

**代码#4 :**

```py
static PyObject *py_func(PyObject *self, PyObject *args)
{
    ...
}
```

*   **对象**–代表任何 Python 对象的 C 数据类型。在很高的层次上，扩展函数是接收 Python 对象元组(在 `PyObject *args`中)并作为结果返回新 Python 对象的 C 函数。函数的 self 参数对于简单的扩展函数来说是不使用的，但是如果你想在 c 语言中定义新的类或对象类型，它就开始起作用了。
*   **`PyArg_ParseTuple()`** 函数用于将 Python 中的值转换为 C 表示。作为输入，它接受一个格式字符串，该字符串指示所需的值，例如整数的“I”和双精度的“d”，以及放置转换结果的 C 变量的地址。
*   **`Py_BuildValue()`** 函数用于从 C 数据类型创建 Python 对象。它还接受一个格式代码来指示所需的类型。在扩展函数中，它用于将结果返回给 Python。`Py_BuildValue()`的一个特点是可以构建更复杂种类的对象，比如元组和字典。