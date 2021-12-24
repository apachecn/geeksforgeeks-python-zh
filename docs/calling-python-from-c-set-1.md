# 从 C |集 1 调用 Python

> 原文:[https://www.geeksforgeeks.org/calling-python-from-c-set-1/](https://www.geeksforgeeks.org/calling-python-from-c-set-1/)

在本文中，我们将主要关注从 C 安全执行 Python 可调用，将结果返回给 C，并编写需要访问 Python 函数作为回调的 C 代码。

下面的代码集中在从 c 语言调用 Python 所涉及的棘手部分。

**代码# 1:[第 1 步和第 2 步]拥有 GIL 并验证该函数是可正确调用的**

```
#include <Python.h>

/* Execute func(x, y) in the Python interpreter. The
arguments and return result of the function must
be Python floats */

double call_func(PyObject *func, double x, double y)
{
    PyObject *args;
    PyObject *kwargs;
    PyObject *result = 0;
    double retval;

    // Make sure we own the GIL
    PyGILState_STATE state = PyGILState_Ensure();

    // Verify that func is a proper callable
    if (!PyCallable_Check(func))
    {
        fprintf(stderr, "call_func: expected a callable\n");
        goto fail;
    }
```

**代码#2:构建参数，调用函数，检查 Python 异常**

创建返回值，恢复以前的 GIL 状态并返回。

```
    // Step3
    args = Py_BuildValue("(dd)", x, y);
    kwargs = NULL;

    // Step 4
    result = PyObject_Call(func, args, kwargs);
    Py_DECREF(args);
    Py_XDECREF(kwargs);

    // Step 5
    if (PyErr_Occurred())
    {
        PyErr_Print();
        goto fail;
    }

    // Verify the result is a float object 
    if (!PyFloat_Check(result))
    {
        fprintf(stderr, "call_func: callable didn't return a float\n");
        goto fail;
    }

    // Step 6
    retval = PyFloat_AsDouble(result);
    Py_DECREF(result);

    // Step 7
    PyGILState_Release(state);
    return retval;
    fail:
        Py_XDECREF(result);
        PyGILState_Release(state);
        abort(); 
}
```

要使用这个函数，需要传入对现有 Python 可调用的引用。要做到这一点，有很多方法，比如简单地编写 C 代码，从现有模块中提取一个符号，或者将一个可调用对象传递到扩展模块中。

下面给出的代码显示了从嵌入式 Python 解释器调用函数。

**代码#3:从模块**加载符号

```
#include <Python.h>
/* Definition of call_func() same as above */

/* Load a symbol from a module */
PyObject *import_name(const char *modname, const char *symbol)
{
    PyObject *u_name, *module;
    u_name = PyUnicode_FromString(modname);
    module = PyImport_Import(u_name);
    Py_DECREF(u_name);

    return PyObject_GetAttrString(module, symbol);
}
```