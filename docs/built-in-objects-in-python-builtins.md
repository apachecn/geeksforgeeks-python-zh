# Python 内置的内置对象

> 原文:[https://www . geeksforgeeks . org/内置 python 对象内置/](https://www.geeksforgeeks.org/built-in-objects-in-python-builtins/)

这个 Python 模块提供了对 Python 所有“内置”标识符的直接访问。*例如*、**内置. open** 是内置函数的全称`open().`这个模块通常不会被大多数应用程序显式访问，但是在提供与内置值同名的对象的模块中可能会很有用，但是在这些模块中也需要该名称的内置。

**例如**，在一个想要实现包裹内置 open()的`open()`功能的模块中，这个模块可以直接使用:

```py
open(path, 'r')
```

但是，如果有一个函数与内置函数同名，则需要显式调用这些函数:

```py
def open(path):
    f = builtins.open(path, 'r')

```

这里第一个开放函数是由程序员定义的，第二个是从内置模块导入的。

**示例:**

```py
# without explicitly calling 
# the builtins module
print(round(3.14))

# explicitly calling the 
# builtins module
import builtins

a = builtins.round(3.14)
print(a)
```

**输出:**

```py
3
3
```

需要记住的一件更有趣的事情是，编译器对内置模块包含的预定义函数的用户定义版本给予了更高的优先级。因此，如果一个程序包含对这两种程序的调用，那么用户定义的程序将被调用。要调用预定义的版本，应该使用 builtins 关键字。

**示例:**

```py
import builtins

def pow():

    print("inside user-defined function pow() \
    to calculate 2**3 ")
    val = 2

    for i in range(1, 3, 1):
        val=val*2

    return val

def main():

    print("calling for pre-defined version of pow() \
    from builtins module to calculate 2**3 ")

    print(builtins.pow(2, 3))
    a = pow()
    print(a)

# Driver Code
main()
```

**输出:**

> 从内置模块调用预定义版本的 pow()来计算用户定义函数 pow()中的 2**3
> 8
> 来计算 2**3
> 8

#### 内置模块的内容

这个模块在每次解释器启动时都会自动加载，这就是为什么它通常不会被显式调用的原因。内建定义了以下内容:

*   **对象类**–所有 python 对象的基类
*   **所有内置数据类型类**–所有数据类型，如数字、字符串、列表等。
*   **内置异常类**–如 BaseException 类等。
*   **内置功能**–像 open()，abs()，all()，等功能。
*   **内置常数**–假、真等常数。

#### 内置数据类型类

*   **真值测试-** 检查代码有效性的陈述和条件。
*   **BOOLEAN OPERATIONS-** 和，或，否。
*   **COMPLATIONS-**=，==，！=，是和不是。
*   **数值类型-** int、float、复杂和按位运算，如 and、or、exclusive or、shifts 和 inverse。
*   **迭代器类型-** 与容器迭代相关的操作。
*   **序列类型-** 列表、元组、范围和对这些的操作。
*   **TEXT SEQUENCE TYPE-** 与字符串突变和显示相关的字符串和方法。
*   **二进制序列类型-** 字节，字节数组和内存视图。
*   **设置类型-** 设置和 frozenset。
*   **绘制类型图-** 字典。
*   **CONTEXT MANAGER TYPES-** 运行时上下文相关事宜。
*   **其他–**模块、实例、空对象、

**示例**:描述内置类型应用的简单程序

```py
a =[1, 2, 3, 4]

for i in a:

    if i == 3:
        print("found")
    else:
        print("not found")
```

**输出:**

```py
not found
not found
found
not found
```

**内置功能**

| abs() | delattr() | 哈希() | memoryview() | 设置() |
| 全部() | dict() | 帮助() | 最小值() | setattr（） |
| 任何() | dir() | 十六进制() | 下一个() | 切片() |
| ascii() | 时髦版() | id() | 对象() | 已排序() |
| bin() | 枚举() | 输入() | 十月() | staticmethod() |
| bool() | eval() | int() | 打开() | str() |
| 断点() | exec() | 实例() | 订单() | 总和() |
| 字节数组（） | 过滤器() | issubclass() | 功率() | 超级() |
| 字节数() | 浮动() | iter() | 打印() | 元组() |
| 可调用() | 格式() | len() | 属性() | 类型() |
| chr() | frozenset() | 列表() | 范围() | vars() |
| classmethod() | getattr（） | 本地人() | repr() | zip() |
| 编译() | 全球() | 地图() | 反转() | __ 导入 _ _() |
| 复杂的 | hasattr() | 最大值() | 圆形() |  |