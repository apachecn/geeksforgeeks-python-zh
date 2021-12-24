# 使用 Coden 模块进行二进制、十六进制和十进制数字之间的转换

> 原文:[https://www . geesforgeks . org/二进制-十六进制-十进制-数字之间的转换-使用-coden-module/](https://www.geeksforgeeks.org/conversion-between-binary-hexadecimal-and-decimal-numbers-using-coden-module/)

Coden 是一个基于代码、秘密代码的库。该库可用于编码和解码，以便秘密发送消息。它也可以用于 Python 中二进制、十六进制和十进制数字之间的转换。

#### 装置

这个模块没有内置 Python。要安装它，请在终端中键入以下命令。

```
pip install coden

```

## 二进制、十六进制和十进制数之间的转换

**十进制到二进制:**这个模块提供了一个名为 int_to_bin()的内置 int 方法来做同样的事情。

**示例:**

## 蟒蛇 3

```
import coden

a_decimal_number = 16227
binary_output = coden.int_to_bin(a_decimal_number)
print(binary_output)
```

**输出:**

```
11111101100011
```

**十进制到十六进制:**这个模块提供了一个名为 int_to_hex()的内置 int 方法来完成同样的操作。

**示例:**

## 蟒蛇 3

```
import coden

a_decimal_number = 165
hexadecimal_output = coden.int_to_hex(a_decimal_number)
print(hexadecimal_output)
```

**输出:**

```
a5
```

**二进制到十六进制:**这个模块提供了一个内置的 int 方法，叫做 bin_to_hex()来完成同样的操作。

**示例:**

## 蟒蛇 3

```
import coden

a_binary_number = 110100
hexadecimal_output = coden.bin_to_hex(a_binary_number)
print(hexadecimal_output)
```

**输出:**

```
34
```

**二进制到十进制:**这个模块提供了一个内置的 int 方法，叫做 bin_to_int()来做同样的事情。

**示例:**

## 蟒蛇 3

```
import coden

a_binary_number = 10010
decimal_output = coden.bin_to_int(a_binary_number)
print(decimal_output)
```

**输出:**

```
18
```

**十六进制到二进制:**这个模块提供了一个名为 hex_to_bin()的内置 int 方法来做同样的事情。

**示例:**

## 蟒蛇 3

```
import coden

a_hexadecimal_number = "f1ff"
binary_output = coden.hex_to_bin(a_hexadecimal_number)
print(binary_output)
```

**输出:**

```
1111000111111111
```

**十六进制到十进制:**这个模块提供了一个名为 hex_to_int()的内置 int 方法来完成同样的操作。

**示例:**

## 蟒蛇 3

```
import coden

a_hexadecimal_number = "ffea1a"
decimal_output = coden.hex_to_int(a_hexadecimal_number)
print(decimal_output)
```

**输出:**

```
16771610
```

### 使用代码模块的随机数

**随机十六进制:**函数 randoms .十六进制返回给定十六进制数范围之间的随机十六进制数。

**示例:**

## 蟒蛇 3

```
import coden

a = "f"
b = "1e"

# returns random hexadecimal in range 
# of a - b.
random_hexadecimal_output = coden.randoms.hexadecimal(a, b)
print(random_hexadecimal_output)
```

**输出:**

```
15
```

**随机二进制:**函数 randoms.binary 返回给定二进制数范围之间的随机二进制数。

**示例:**

## 蟒蛇 3

```
import coden

a = 101
b = 10101

# returns random binary in range 
# of a - b.
random_hexadecimal_output = coden.randoms.binary(a, b)
print(random_hexadecimal_output)
```

**输出:**

```
110
```

**随机十六进制颜色:** randoms.hexcolor()返回随机十六进制数(颜色)。

**示例:**

## 蟒蛇 3

```
import coden

# returns random hexadecimal color
random_hexadecimal_color_output = coden.randoms.hexcolor()
print(random_hexadecimal_color_output)
```

**输出:**

```
#63783A
```