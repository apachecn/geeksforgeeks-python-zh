# Python | cmath.log10()方法

> 原文:[https://www.geeksforgeeks.org/python-cmath-log10-method/](https://www.geeksforgeeks.org/python-cmath-log10-method/)

借助`**cmath.log10()**`方法，通过传递给`cmath.log10()`方法，我们可以找到任何基数为-10 的对数的值。

> **语法:** `cmath.log10(value)`
> **返回:**返回基数-10 的日志值。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`cmath.log10()`方法，我们能够通过向具有 base-10 的 log 传递任何值来获得它的值。

```py
# importing cmath library
import cmath

# using cmath.log10() method
gfg = cmath.log10(7)

print(gfg)
```

**输出:**

> (0.8450980400142567+0j)

**例 2 :**

```py
# importing cmath library
import cmath

# using cmath.log10() method
gfg = cmath.log10(25)

print(gfg)
```

**输出:**

> (1.3979400086720375+0j)