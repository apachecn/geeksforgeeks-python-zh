# Python 中扩展模块的 C API 集合 1

> 原文:[https://www . geesforgeks . org/c-API-from-extension-module-in-python-set-1/](https://www.geeksforgeeks.org/c-api-from-extension-module-in-python-set-1/)

假设给定一个 C 扩展模块，该模块在内部定义了各种有用的函数，这些函数可以作为公共 C API 导出，供其他地方使用。如果我们想在其他扩展模块中使用这些函数。然后，知道如何将它们链接在一起是很重要的，但是用 C 编译器/链接器来做似乎过于复杂。

**代码# 1:【C 代码】包含一些实用功能的点对象**

```
# Destructor function for points
static void del_Point(PyObject *obj)
{
    free(PyCapsule_GetPointer(obj, "Point"));
}

static PyObject *PyPoint_FromPoint(Point *p, int must_free)
{
    return PyCapsule_New(p, "Point", must_free ? del_Point : NULL);
}

# Utility functions 
static Point *PyPoint_AsPoint(PyObject *obj)
{
    return (Point *) PyCapsule_GetPointer(obj, "Point");
}
```

现在要处理的问题是如何将`**PyPoint_AsPoint()**`和`**PyPoint_FromPoint()**`函数导出为一个可以被其他扩展模块使用并链接到其他扩展模块的应用编程接口。(**例如**–任何其他扩展也要使用包装的点对象)。

**代码#2:为`**work**`扩展名引入一个名为`**Pythonsample.h**`的新头文件。**

```
//pythonsample.h
#include "Python.h"
#include "work.h"
#ifdef __cplusplus

extern "C" {
#endif

// Public API Table
    typedef struct
    {
        Point *(*aspoint)(PyObject *);
        PyObject *(*frompoint)(Point *, int);
    } _PointAPIMethods;

#ifndef PYTHONSAMPLE_MODULE

    /* Method table in external module */
    static _PointAPIMethods *_point_api = 0;
```

**代码#3:从【工作】**导入 API 表

```
static int import_sample(void)
{
    _point_api = (_PointAPIMethods *) PyCapsule_Import("work._point_api", 0);
    return (_point_api != NULL) ? 1 : 0;
}
/* Macros to implement the programming interface */
#define PyPoint_AsPoint(obj) (_point_api->aspoint)(obj)
#define PyPoint_FromPoint(obj) (_point_api->frompoint)(obj)
#endif
#ifdef __cplusplus
}
#endif
```

*_PointAPIMethods* 函数指针表是最重要的功能，因为它将在导出模块中初始化，并通过导入模块找到。下面的代码显示了如何更改原始扩展模块来填充表并导出它。

**代码#4:析构函数和效用函数**

```
// pythonsample.c
# include "Python.h"
# define PYTHONSAMPLE_MODULE
# include "pythonsample.h"

// Destructor function for points 
static void del_Point(PyObject * obj)
{
    printf("Deleting point\n");
    free(PyCapsule_GetPointer(obj, "Point"));
}

// Utility functions
static Point * PyPoint_AsPoint(PyObject * obj)
{
    return (Point *) PyCapsule_GetPointer(obj, "Point");
}

static PyObject * PyPoint_FromPoint(Point * p, int free)
{
    return PyCapsule_New(p, "Point", free ? del_Point : NULL);
}

static _PointAPIMethods _point_api =
{
    PyPoint_AsPoint,
    PyPoint_FromPoint
};
```

**代码#5:模块功能**

```
// Module initialization function 

PyMODINIT_FUNC
PyInit_sample(void)
{
    PyObject *m;
    PyObject *py_point_api;
    m = PyModule_Create(&samplemodule);
    if (m == NULL)
        return NULL;

    // Add the Point C API functions
    py_point_api = PyCapsule_New((void *) &_point_api, "work._point_api", NULL);
    if (py_point_api)
    {
        PyModule_AddObject(m, "_point_api", py_point_api);
    }
    return m;
}
```