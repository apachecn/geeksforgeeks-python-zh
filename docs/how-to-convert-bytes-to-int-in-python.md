# Python 中如何将字节转换为 Int？

> 原文:[https://www . geesforgeks . org/如何在 python 中将字节转换为 int/](https://www.geeksforgeeks.org/how-to-convert-bytes-to-int-in-python/)

使用 Python 可以轻松地将字节对象转换为整数值。Python 为我们提供了各种内置方法，如 from_bytes()以及实现这种相互转换的类。

## **int.from_bytes()方法**

通过使用 int.from_bytes()方法，字节值可以交换为 int 值。此方法至少需要 Python 3.2，并且具有以下语法:

> **语法:** int.from_bytes(字节，byteorder，*，有符号=False)
> 
> **参数:**
> 
> *   **字节–**一个字节对象
> *   **byte order–**确定整数值的表示顺序。byteorder 的值可以是“小”，最高有效位存储在末尾，最低有效位存储在开头，也可以是“大”，MSB 存储在开头，LSB 存储在结尾。大字节顺序计算基数为 256 的整数值。
> *   **有符号–**默认值–假。指示是否表示数字的二进制补码。
> 
> **返回–**一个等于给定字节的整数

以下代码片段指示字节到 int 对象的转换。

**例 1:**

## 蟒蛇 3

```
# declaring byte value
byte_val = b'\x00\x01'

# converting to int
# byteorder is big where MSB is at start
int_val = int.from_bytes(byte_val, "big")

# printing int equivalent
print(int_val)
```

**输出:**

```
1
```

**例 2:**

## 蟒蛇 3

```
byte_val = b'\x00\x10'

int_val = int.from_bytes(byte_val, "little")

# printing int object
print(int_val)
```

**输出:**

```
4096
```

**例 3:**

## 蟒蛇 3

```
byte_val = b'\xfc\x00'

# 2's complement is enabled in big 
# endian byte order format
int_val = int.from_bytes(byte_val, "big", signed="True")

# printing int object
print(int_val)
```

**输出:**

```
-1024
```