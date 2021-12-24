# Python 中如何将 Int 转换为 Bytes？

> 原文:[https://www . geesforgeks . org/如何在 python 中将 int 转换为 bytes/](https://www.geeksforgeeks.org/how-to-convert-int-to-bytes-in-python/)

int 对象可以用来以字节的格式表示相同的值。整数代表一个字节，存储为数组，其最高有效位(MSB)存储在数组的开头或结尾。

**方法 1:**int to bytes()

可以使用 **int.to_bytes()方法将一个 int 值转换为字节。**该方法是在 int 值上调用的，Python 2(要求最小 Python3)不支持该方法执行。

> **语法:** int.to_bytes(长度，byteorder)
> 
> **论据**:
> 
> 长度–所需的数组长度，以字节为单位。
> 
> byte order–执行 int 到字节转换的数组顺序。byteorder 的值可以是**“小”**，其中最高有效位存储在末尾，最少存储在开头，也可以是**“大”**，其中 MSB 存储在开头，LSB 存储在结尾。
> 
> **异常:**
> 
> 如果整数值长度不足以容纳在数组的长度中，则返回 OverflowError。

以下程序说明了该方法在 Python 中的用法:

## 蟒蛇 3

```
# declaring an integer value
integer_val = 5

# converting int to bytes with length 
# of the array as 2 and byter order as big
bytes_val = integer_val.to_bytes(2, 'big')

# printing integer in byte representation
print(bytes_val)
```

**Output**

```
b'\x00\x05'
```

## 蟒蛇 3

```
# declaring an integer value
integer_val = 10

# converting int to bytes with length 
# of the array as 5 and byter order as 
# little
bytes_val = integer_val.to_bytes(5, 'little')

# printing integer in byte representation
print(bytes_val)
```

**Output**

```
b'\n\x00\x00\x00\x00'
```

**方法 2:** 将整数转换为字符串，将字符串转换为字节

这种方法在 Python 版本 2 和 3 中都是兼容的。此方法不将数组和 byteorder 的长度作为参数。

*   以十进制格式表示的整数值可以首先使用 str()函数转换为字符串，该函数将要转换为相应等效字符串的整数值作为参数。
*   然后，通过为每个字符选择所需的表示形式，也就是对字符串值进行编码，将这个等效字符串转换为字节序列。这是通过 str.encode()方法完成的。

## 蟒蛇 3

```
# declaring an integer value
int_val = 5

# converting to string
str_val = str(int_val)

# converting string to bytes
byte_val = str_val.encode()
print(byte_val)
```

**Output**

```
b'5'
```