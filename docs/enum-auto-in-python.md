# Python 中的 enum.auto()

> 原文:[https://www.geeksforgeeks.org/enum-auto-in-python/](https://www.geeksforgeeks.org/enum-auto-in-python/)

借助`**enum.auto()**`方法，我们只需使用`enum.auto()`方法就可以自动得到赋值的整数值。

> **语法:** `enum.auto()`
> 
> **自动将整数值赋给枚举类属性的值。**

**示例#1 :**
在这个示例中，我们可以看到，通过使用`enum.auto()`方法，我们能够使用该方法将数值自动分配给类属性。

```
# import enum and auto
from enum import Enum, auto

# Using enum.auto() method
class language(Enum):
    Java = auto()
    Python = auto()
    HTML = auto()

print(list(language))
```

**输出:**

> [,, ]

**例 2 :**

```
# import enum and auto
from enum import Enum, auto

# Using enum.auto() method
class language(Enum):
    Cpp = auto()
    JavaScript = auto()
    Java = auto()
    Python = auto()
    HTML = auto()

print(list(language))
```

**输出:**

> [,,,, ]