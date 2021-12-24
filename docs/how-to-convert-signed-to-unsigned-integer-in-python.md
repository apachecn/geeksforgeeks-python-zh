# Python 中有符号到无符号整数如何转换？

> 原文:[https://www . geesforgeks . org/如何在 python 中将有符号整数转换为无符号整数/](https://www.geeksforgeeks.org/how-to-convert-signed-to-unsigned-integer-in-python/)

Python 包含内置的数字数据类型，如 int(整数)、float 和 complex。与 C 编程相比，Python 没有有符号和无符号整数作为数据类型。在 python 中没有必要为变量指定数据类型，因为解释器本身会根据分配给该变量的值来预测变量的数据类型。python 中的 int 数据类型与有符号整数完全相同。有符号整数是介于**-(2^31 =-2147483648 到(2^31)–1 = 2147483647**之间的 32 位整数，包含正数或负数。它用二进制补码表示。无符号整数是 0 到 2^32-1.范围内的 32 位非负整数(0 或正数)因此，在本文中，让我们知道如何在 python 中将有符号整数转换为无符号整数。

**示例 1:** 将 2^32(or 1 < < 32)添加到有符号整数中，将其转换为无符号整数

## 蟒蛇 3

```py
signed_integer = -100

# Adding 2^32 to convert signed to unsigned integer
unsigned_integer = signed_integer+2**32
print(unsigned_integer)
print(type(unsigned_integer))
```

**输出:**

```py
4294967196
<class 'int'>
```

**示例 2:** 使用按位左移(< <)运算符

**按位左移:**它通过向左移动数字的左操作数位来执行位操作，并因此填充左侧的 0。

例如，x << y

将带有“y”整数的整数“x”左移 y 位。这与 x 乘以 2 再乘以 y 的幂(2**y)是一样的。

## 蟒蛇 3

```py
signed_integer = -1

# Adding 1<<32 to convert signed to 
# unsigned integer
unsigned_integer = signed_integer+(1 << 32)
print(unsigned_integer)
```

**输出:**

```py
4294967295
```

**例 3:**

## 蟒蛇 3

```py
signed_integer = -10

# Adding 1<<32 to convert signed to
# unsigned integer
unsigned_integer = signed_integer+(1 << 32)
print(unsigned_integer)
```

**输出:**

```py
4294967286
```