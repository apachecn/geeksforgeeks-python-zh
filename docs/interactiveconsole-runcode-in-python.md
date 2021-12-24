# Python 中的 InteractiveConsole runcode()

> 原文:[https://www . geesforgeks . org/interactive console-run code-in-python/](https://www.geeksforgeeks.org/interactiveconsole-runcode-in-python/)

借助`**InteractiveConsole.runcode()**`方法，我们可以得到单行或多行代码的输出，如果我们想看到部分代码的结果，那么我们可以使用`InteractiveConsole.runcode()`方法。

> **语法:** `InteractiveConsole.runcode(code)`
> 
> **返回:**返回代码段的输出。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`InteractiveConsole.runcode()`方法，我们能够获得部分代码的结果，而无需使用该方法运行整个代码。

```py
# import code
from code import InteractiveConsole

code = 'print("GeeksForGeeks")'
# Using InteractiveConsole.runcode() method
InteractiveConsole().runcode(code)
```

**输出:**

> 极客们

**例 2 :**

```py
# import code
from code import InteractiveConsole

code = 'a = 10; print(a + 20)'
# Using InteractiveConsole.runcode() method
InteractiveConsole().runcode(code)
```

**输出:**

> Thirty