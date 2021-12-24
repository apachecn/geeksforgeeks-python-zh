# 使用单一调度功能工具的功能重载

> 原文:[https://www . geeksforgeeks . org/function-overload-with-single dispatch-func tools/](https://www.geeksforgeeks.org/function-overloading-with-singledispatch-functools/)

**单一分派**泛型函数装饰器将一个函数转换为泛型函数，根据其第一个参数的类型，泛型函数可以有不同的行为。修饰函数充当默认实现。要向函数添加重载实现，请使用泛型函数的 **register()属性**。它是一个装饰器，接受一个类型参数并装饰一个实现该类型操作的函数。

如果没有特定类型的注册实现，则使用其方法解析顺序来查找更通用的实现。用 **@singledispatch** 修饰的原始函数是为基对象类型注册的，这意味着如果找不到更好的实现就使用它。

```
from functools import singledispatch

@singledispatch
def fun(s):
    print(s)

@fun.register(int)
def _1(s):
    print(s * 2)

@fun.register(list)
def _2(s):
    for i, e in enumerate(s):print(i, e)

fun('GeeksforGeeks')
fun(10)
fun(['g', 'e', 'e', 'k', 's'])
```

**输出:**

```
GeeksforGeeks
20
0 g
1 e
2 e
3 k
4 s

```

singledispatch 装饰器还支持装饰器堆叠。这允许我们创建一个可以处理多种类型的重载函数。示例–

```
from functools import singledispatch
from decimal import Decimal

@singledispatch
def fun(s):
    print(s)

@fun.register(float)
@fun.register(Decimal)
def _3(s):
    print(round(s, 2))

fun(2.34)
fun(Decimal(4.897))
```

**输出:**

```
2.34
4.90

```

**调度()–**检查泛型函数将为给定类型选择哪种实现。

```
print(fun.dispatch(dict))
print(fun.dispatch(list))
```

**输出:**

```
<function fun at 0x0000022CFE62C7B8>
<function _2 at 0x0000022CFE77BA60>

```

**registry()–**只读属性，访问所有注册的实现。

```
print(fun.registry.keys())
print(fun.registry[int])
print(fun.registry[object])
```

**输出:**

```
dict_keys([<class 'object'>, <class 'int'>, <class 'list'>])
<function _1 at 0x0000018E5480B9D8>
<function fun at 0x0000018E546BC7B8>

```