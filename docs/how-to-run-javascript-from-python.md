# 如何从 Python 运行 Javascript？

> 原文:[https://www . geesforgeks . org/how-run-JavaScript-from-python/](https://www.geeksforgeeks.org/how-to-run-javascript-from-python/)

在本文中，我们将讨论如何用 Python 运行 javascript 文件。为此，我们将使用 **JS2PY** ( **纯 Python 中的 Javascript 运行时** ) Python 模块。JS2PY 的工作原理是将 JavaScript 直接翻译成 Python。它表明您可以直接从 Python 代码运行 JS，而无需安装像 **V8** 这样的大型外部引擎。

要使用该模块，首先必须将其安装到系统中，因为它不是内置的。

**语法:**

```py
pip install js2py
```

要使用该模块，必须将其导入。

**语法:**

```py
import js2py
```

现在，为了将 javascript 转换为 python，javascript 命令作为字符串存储在某个变量中。我们现在将使用模块 **js2py** 的 **eval_js()函数**，并将 javascript 代码传递给它。

**eval_js()** 函数在 js2py 模块下定义，用于评估 javascript 代码，在 **eval_js** 模块中将 Javascript 代码作为参数传递。

**语法:**

> js 2 py . eval _ js(JavaScript 代码)
> 
> t5]

**示例:**在 Python 中运行一个简单的 JS 命令

## **Python 3**

```py
import js2py

code_2 = "function f(x) {return x+x;}"
res_2 = js2py.eval_js(code_2)

print(res_2(5))
```