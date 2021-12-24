# 枚举。Python 中的 IntEnum

> 哎哎哎:# t0]https://www . geeksforgeeks . org/enum-intenum-in-python/

借助`**enum.IntEnum()**`方法，我们可以得到基于整数值的枚举，如果与普通的基于枚举的类进行比较，使用`enum.IntEnum()`方法会失败。

> **语法:** `enum.IntEnum`
> 
> **Return :** IntEnum 没有写类型。

**示例#1 :**
在这个示例中我们可以看到，通过使用`enum.IntEnum()`方法，我们能够通过使用该方法获得基于整数值的枚举。

```py
# import enum and IntEnum
from enum import IntEnum

# Using enum.IntEnum 
class author(IntEnum):
     GEEK = 1
     FOR = 2
     GEEKS = 3

print(author.FOR == 2)
```

**OutPut :**

> 真实的

**例 2 :**

```py
# import enum and IntEnum
from enum import IntEnum, Enum

# Using enum.IntEnum 
class author(IntEnum):
     GEEK = 1
     FOR = 2
     GEEKS = 3

class language(Enum):
     Python = 1
     Java = 2

print(author.GEEK == language.Python)
```

**OutPut :**

> 错误的