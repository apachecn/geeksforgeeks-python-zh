# Python 中的 InteractiveInterpreter runsource()

> 原文:[https://www . geesforgeks . org/interactive interpreter-run source-in-python/](https://www.geeksforgeeks.org/interactiveinterpreter-runsource-in-python/)

借助`**InteractiveInterpreter.runsource()**`方法，我们可以使用`InteractiveInterpreter.runsource()`方法编译运行单行或多行的源码。

> **语法:** `InteractiveInterpreter.runsource(code)`
> 
> **返回:**如果编译成功则返回输出，否则返回错误。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`InteractiveInterpreter.runsource()`方法，我们能够编译并运行这段代码，如果运行成功，我们可以使用该方法获得结果 else false。

```py
# import code and InteractiveInterpreter
from code import InteractiveInterpreter

code = 'print("GeeksForGeeks")'
# Using InteractiveInterpreter.runsource() method
InteractiveInterpreter().runsource(code)
```

**输出:**

> 极客们

**例 2 :**

```py
# import code and InteractiveInterpreter
from code import InteractiveInterpreter

code = 'a = 8; b = 2.5; -a = a + b'
# Using InteractiveInterpreter.runsource() method
InteractiveInterpreter().runsource(code)
```

**输出:**

> 语法错误:无法分配给运算符
> False