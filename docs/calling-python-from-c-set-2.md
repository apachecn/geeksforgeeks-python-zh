# 从 C | Set 2 调用 Python

> 原文:[https://www.geeksforgeeks.org/calling-python-from-c-set-2/](https://www.geeksforgeeks.org/calling-python-from-c-set-2/)

先决条件:[从 C | Set 1 调用 Python](https://www.geeksforgeeks.org/calling-python-from-c-set-1/)

要使用这个函数，需要传入对现有 Python 可调用的引用。要做到这一点，有很多方法，比如简单地编写 C 代码，从现有模块中提取一个符号，或者将一个可调用对象传递到扩展模块中。

**代码#1:简单嵌入示例**

```py
int main()
{
    PyObject * pow_func;
    double x;
    Py_Initialize();

    // Get a reference to the math.pow function
    pow_func = import_name("math", "pow");

    // Call it using our call_func() code 
    for (x = 0.0; x < 10.0; x += 0.1)
    {
        printf("% 0.2f % 0.2f\n", x, call_func(pow_func, x, 2.0));
    }

    Py_DECREF(pow_func);
    Py_Finalize();
    return 0;
}
```

要构建最后这个例子，需要编译 C 并链接到 Python 解释器。下面的代码片段展示了如何做到这一点(这可能需要在您的机器上进行一些修改):

**代码#2 :**

```py
all::
cc -g embed.c -I/usr/local/include/python3.3m \
-L /usr/local/lib/python3.3/config-3.3m -lpython3.3m
```

**编译并运行生成的可执行文件给出如下输出:**

```py
0.00 0.00
0.10 0.01
0.20 0.04
0.30 0.09
0.40 0.16
...

```

下面的代码给出了另一个例子，它显示了一个扩展函数，该函数接收一个可调用的和一些参数，并将它们传递给`**call_func()**`进行测试。

**代码#3 :**

```py
/* Extension function for testing the C-Python callback */

PyObject * py_call_func(PyObject * self, PyObject * args)
{
    PyObject * func;

    double x, y, result;
    if (! PyArg_ParseTuple(args, "Odd", &func, &x, &y))
    {
        return NULL;
    }
    result = call_func(func, x, y);
    return Py_BuildValue("d", result);
}
```

**代码#4:测试扩展功能**

```py
import work

def add(x, y):
    return x + y

work.call_func(add, 3, 4)
```

**输出:**

```py
7.0

```

至关重要的是，首先我们需要一个 Python 对象来表示要调用的可调用对象。这可能是一个函数、类、方法、内置方法或任何实现`**__call__()**` 操作的东西。要验证它是否是可调用函数，请使用`**PyCallable_Check()**`。

**代码#5:检查`PyCallable_Check()`功能**

```py
double call_func(PyObject *func, double x, double y)
{
    ...
    // Verify that func is a proper callable
    if (!PyCallable_Check(func))
    {
        fprintf(stderr, "call_func: expected a callable\n");
        goto fail;
    }
    ...
```

只需使用`**PyObject_Call()**`调用一个函数，为它提供可调用对象、一组参数和一个可选的关键字参数字典。

`**Py_BuildValue()**` 可用于构建自变量元组或字典。

**代码#6 :**

```py
double call_func(PyObject *func, double x, double y)
    {
        PyObject *args;
        PyObject *kwargs;

        /* Build arguments */
        args = Py_BuildValue("(dd)", x, y);
        kwargs = NULL;
        /* Call the function */
        result = PyObject_Call(func, args, kwargs);
        Py_DECREF(args);
        Py_XDECREF(kwargs);

        /* Check for Python exceptions (if any) */
        if (PyErr_Occurred())
        {
            PyErr_Print();
            goto fail;
        }

    fail:
        PyGILState_Release(state);
        abort();

    }
```