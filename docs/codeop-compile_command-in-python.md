# Python 中的 codeop . compile _ command

> 原文:[https://www . geesforgeks . org/codeop-compile _ command-in-python/](https://www.geeksforgeeks.org/codeop-compile_command-in-python/)

借助`**codeop.compile_command()**`方法，我们可以通过使用`codeop.compile_command()`方法编译单行或多行代码来检查语法错误。

> **语法:** `codeop.compile_command(code)`
> 
> **返回:**返回对象或编译错误(如果有)。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`codeop.compile_command()`方法，我们能够使用该方法编译多行代码。

```
# import codeop
from codeop import compile_command

code = 'a = 5 b = 9; print(a + b)'
# Using codeop.compile_command() method
compile_command(code) 
```

**输出:**

> a = 5 b = 9；打印(a + b)
> ^
> 语法错误:无效语法

**例 2 :**

```
# import codeop
from codeop import compile_command

code = '-a = 5'
# Using codeop.compile_command() method
compile_command(code) 
```

**输出:**

> 语法错误:无法分配给运算符