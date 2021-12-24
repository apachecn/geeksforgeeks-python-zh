# Python 中的 InteractiveInterpreter runcode()

> 原文:[https://www . geesforgeks . org/interactive interpreter-run code-in-python/](https://www.geeksforgeeks.org/interactiveinterpreter-runcode-in-python/)

借助`**InteractiveInterpreter.runcode()**`方法，我们只能使用`InteractiveInterpreter.runcode()`方法执行预编译的单行或多行源代码。

> **语法:** `InteractiveInterpreter.runcode(code)`
> **返回:**返回执行源 else 错误的结果。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`InteractiveInterpreter.runcode()`方法，我们能够执行这段代码，如果运行成功，我们可以使用该方法获得结果否则会出错。

```
# import code and InteractiveInterpreter
import code
from code import InteractiveInterpreter

source = 'print("GeeksForGeeks")'
compile_code = code.compile_command(source)

# Using InteractiveInterpreter.runcode() method
InteractiveInterpreter().runcode(compile_code)
```

**输出:**

> 极客们

**例 2 :**

```
import code
from code import InteractiveInterpreter

source = 'a = 5; b = 5; li = [a * b for i in range(5)]; print(li)'
compile_code = code.compile_command(source)

# Using InteractiveInterpreter.runcode() method
InteractiveInterpreter().runcode(compile_code)
```

**输出:**

> [25, 25, 25, 25, 25]