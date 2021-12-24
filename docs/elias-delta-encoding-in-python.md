# Python 中的 Elias Delta 编码

> 原文:[https://www . geesforgeks . org/Elias-delta-编码-in-python/](https://www.geeksforgeeks.org/elias-delta-encoding-in-python/)

在本文中，我们将使用 python 实现 Elias Delta 编码。

**语法:**

> Elias Delta 编码(X)= Elias Gamma 编码(1+floor(log2(X))) +无 MSB 的 X 的二进制表示。

## 履行

首先，在为 Elias delta 编码编写代码之前，我们将实现 Elias Delta 编码。

**第一步:**

*   从数学库中导入 log、floor 函数来执行对数运算。
*   从用户获取输入 k，以在 Elias Gamma 中编码。
*   使用数学模块中的 floor 和 log 函数，找到 1+floor(log2(X)并将其存储在变量 n 中。
*   找到 N 的一元编码，使用(N-1)*'0'+'1 '，这给我们一个二进制字符串，最低有效位为' 1 '，其余最高有效位为 N-1 '0 '。

**示例:**某些值的 Elias Gamma 编码

## 蟒蛇 3

```py
def EliasGammaEncode(k):
    if (k == 0):
        return '0'
    N = 1 + floor(log(k, 2))
    Unary = (N-1)*'0'+'1'
    return Unary + Binary_Representation_Without_MSB(k)
```

**第二步:**

*   创建一个函数，该函数接受输入 X，并将结果作为 X 的二进制表示，而不使用 MSB。
*   使用“{0:b}”。format(k)找到 k 的二进制等价物，并将其存储在名为 binary 的变量中。
    *   前缀零只是指定应该使用 format()的哪个参数来填充{}。
    *   b 指定参数应转换为二进制形式。
*   返回字符串二进制[1:]，它是没有 MSB 的 X 的二进制表示。

**示例:**无 MSB 的二进制表示

## 蟒蛇 3

```py
def Binary_Representation_Without_MSB(x):
    binary = "{0:b}".format(int(x))
    binary_without_MSB = binary[1:]
    return binary_without_MSB
```

现在我们要为 Elias Delta 编码编写代码

**第三步:**

*   从用户获取输入 k，以在 Elias Delta 中编码。
*   使用数学模块中的 floor 和 log 函数，找到 1+floor(log2(k))。
*   将 1+floor(log2(k)的结果传递给 Elias Gamma 编码函数。

**示例**:某些值的 Elias Delta 编码

## 蟒蛇 3

```py
def EliasDeltaEncode(x):
    Gamma = EliasGammaEncode(1 + floor(log(k, 2)))
    binary_without_MSB = Binary_Representation_Without_MSB(k)
    return Gamma+binary_without_MSB

k = int(input('Enter a number to encode in Elias Delta: '))
print(EliasDeltaEncode(k))
```

**第四步:**

*   得到 Elias Gamma 编码的结果和无 MSB 的 k 的二进制表示
*   连接两个结果并在控制台上打印出来

为某个整数值生成 Elias Delta 编码的完整代码

## 蟒蛇 3

```py
from math import log
from math import floor

def Binary_Representation_Without_MSB(x):
    binary = "{0:b}".format(int(x))
    binary_without_MSB = binary[1:]
    return binary_without_MSB

def EliasGammaEncode(k):
    if (k == 0):
        return '0'
    N = 1 + floor(log(k, 2))
    Unary = (N-1)*'0'+'1'
    return Unary + Binary_Representation_Without_MSB(k)

def EliasDeltaEncode(x):
    Gamma = EliasGammaEncode(1 + floor(log(k, 2)))
    binary_without_MSB = Binary_Representation_Without_MSB(k)
    return Gamma+binary_without_MSB

k =  14
print(EliasDeltaEncode(k))
```

**输出:**

```py
00100110
```