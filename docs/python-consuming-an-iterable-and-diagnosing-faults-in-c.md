# Python |在 C #中消耗可迭代并诊断故障

> 原文:[https://www . geeksforgeeks . org/python-消耗可迭代和诊断故障-in-c/](https://www.geeksforgeeks.org/python-consuming-an-iterable-and-diagnosing-faults-in-c/)

本文旨在编写 C 扩展代码，使用来自任何可迭代对象的项，如列表、元组、文件或生成器。

**代码#1 : C 扩展函数，显示如何消费可迭代表上的项目。**

```py
static PyObject* py_consume_iterable(
    PyObject* self, PyObject* args)
{
    PyObject* obj;
    PyObject* iter;
    PyObject* item;

    if (!PyArg_ParseTuple(args, "O", &obj)) {
        return NULL;
    }

    if ((iter = PyObject_GetIter(obj)) == NULL) {
        return NULL;
    }

    while ((item = PyIter_Next(iter)) != NULL) {
        /* Use item */
        ... Py_DECREF(item);
    }

    Py_DECREF(iter);
    return Py_BuildValue("");
}
```

上面的代码反映了 Python 中类似的代码。 **`PyObject_GetIter()`** 调用与调用 **`iter()`** 获取迭代器相同。 **`PyIter_Next()`** 函数调用迭代器上的下一个方法返回下一个项目，如果没有其他项目，则返回空值。确保您在内存管理方面小心谨慎——**`Py_DECREF()`**需要在生成的项目和迭代器对象本身上调用，以避免泄漏内存。

**诊断分段故障–**
解释器因分段故障、总线错误、访问冲突或其他致命错误而严重崩溃。人们喜欢获得一个 Python 回溯，显示程序在故障点运行的位置。
**故障处理模块**可以帮助您解决这个问题。在程序中包含以下代码。

**代码#2 :**

```py
import faulthandler
faulthandler.enable()
```

或者，使用-Xfaulthandler 选项运行 Python，如下所示:

```py
bash % python3 -Xfaulthandler program.py
```

最后，同样重要的是，可以相应地设置 PYTHONFAULTHANDLER 环境变量。启用 faulthandler 后，C 扩展中的致命错误将导致在失败时打印 Python 回溯。例如:

```py
Fatal Python error: Segmentation fault
Current thread 0x00007fff71106cc0:
File "example.py", line 6 in foo
File "example.py", line 10 in bar
File "example.py", line 14 in spam
File "example.py", line 19 in Segmentation fault 
```

虽然这不能说明 C 代码中哪里出错了，但至少可以说明它是如何从 Python 中出错的。

**faulthandler** 将显示失败时执行的 Python 代码的堆栈追溯。至少，这将显示被调用的顶级扩展函数。借助 *pdb* 或其他 Python 调试器，可以调查导致错误的 Python 代码流。