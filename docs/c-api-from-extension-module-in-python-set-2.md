# Python 中扩展模块的 C API 第 2 集

> 原文:[https://www . geesforgeks . org/c-API-from-extension-module-in-python-set-2/](https://www.geeksforgeeks.org/c-api-from-extension-module-in-python-set-2/)

前提条件:[Python 中扩展模块的 C API 集合 1](https://www.geeksforgeeks.org/c-api-from-extension-module-in-python-set-1/)

让我们看一个新的扩展模块的例子，它加载并使用我们在上一篇文章中构建的这些 API 函数。

**代码#1 :**

```
#include "pythonsample.h"
/* An extension function that uses the exported API */
static PyObject *print_point(PyObject *self, PyObject *args)
{
    PyObject *obj;
    Point *p;
    if (!PyArg_ParseTuple(args, "O", &obj))
    {
        return NULL;
    }
    /* Note: This is defined in a different module */
    p = PyPoint_AsPoint(obj);
    if (!p)
    {
        return NULL;
    }
    printf("%f %f\n", p->x, p->y);
    return Py_BuildValue("");
}

static PyMethodDef PtExampleMethods[] =
{
    {"print_point", print_point, METH_VARARGS, "output a point"},
    { NULL, NULL, 0, NULL}
};

static struct PyModuleDef ptexamplemodule =
{
    PyModuleDef_HEAD_INIT,
    /* name of module */
    "ptexample", 
    /* Doc string (may be NULL) */
    "A module that imports an API", 
    /* Size of per-interpreter state or -1 */
    -1, 
    /* Method table */
    PtExampleMethods 

};
```

**代码#2:模块初始化功能**

```
PyMODINIT_FUNC
PyInit_ptexample(void)
{
    PyObject *m;

    m = PyModule_Create(&ptexamplemodule);

    if (m == NULL)
        return NULL;

    /* Import sample, loading its API functions */
    if (!import_sample())
    {
        return NULL;
    }

    return m;
}
```

现在要编译这个新模块，人们不需要担心如何链接其他模块的任何库或代码。可以简单地使用如下所示的 **`work.py`** 文件。

**代码#3 :**

```
# setup.py
from distutils.core import setup, Extension

# May need pythonsample.h directory
setup(name ='ptexample', 
      ext_modules = [ Extension('ptexample', 
                     ['ptexample.c'], include_dirs = [], )])
```

执行完所有这些任务后，这个新的扩展函数可以与另一个模块中定义的 C API 函数完美地配合工作。

**代码#4:使用其他模块**中定义的 CPI API 函数

```
import ptexample
import work

point1 = work.Point(2, 3)
print ("Point_1 : ", point1)

print ("\n", ptexample.print_point(p1))
```

**输出:**

```
Point_1 : 

2.000000 3.000000

```