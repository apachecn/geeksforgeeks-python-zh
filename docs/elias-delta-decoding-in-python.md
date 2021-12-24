# Python 中的 Elias Delta 解码

> 原文:[https://www . geesforgeks . org/Elias-delta-python 中的解码/](https://www.geeksforgeeks.org/elias-delta-decoding-in-python/)

在本文中，我们将使用 python 实现 Elias Delta 解码。

彼得·埃利亚斯设计了埃利亚斯德尔塔码，这是一个编码正整数的通用系统。

**语法:**

> Elias Delta 编码(X)= Elias Gamma 编码(1+floor(log2(X))) +无 MSB 的 X 的二进制表示。

## **进场:**

*   导入所需的库并从用户处读取编码的二进制字符串。
*   从最高有效位开始读取/计数零的数量，直到看到第一个“1”，并将其存储在名为“L”的变量中

**语法:**

```
L=0
while True:
   if not x[L] == '0':
       break
   L= L + 1
```

*   将“1”视为第一位，读取更多的 1 位，并丢弃所有位，直到当前的 1 位。
*   取出剩余的位，在最高有效位前加上“1”。

**语法:**

> x.insert(0，' 1 ')

*   将最终的二进制数转换成整数，从而得到原始的数字。

### 示例:

> 假设输入的编码字符串是 01111
> 
> **步骤 1:** 从最高有效位读取/计数零的数量，直到看到第一个“1”，并将其存储在“L”中，直到看到第一个“1”
> 
> 在我们的例子中，L=1
> 
> **第二步:**将‘1’视为第一位，多读 L 位(多读 1 位)并丢弃所有内容。
> 
> ~~011~~ 11= 11
> 
> **步骤 3:** 取出剩余的位，并在 MSB 中加上“1”。
> 
> One hundred and eleven
> 
> **步骤 4:** 将最终的二进制字符串转换为整数，这样我们就得到 7。

下面是实现。

**示例 1:** 生成对应于某个值的 Elias Delta 解码值的示例。

## 蟒蛇 3

```
import math

def Elias_Delta_Decoding(x):
    x = list(x)
    L = 0
    while True:
        if not x[L] == '0':
            break
        L = L + 1

    # Reading L more bits and dropping ALL    
    x = x[2*L+1:]  

    # Prepending with 1 in MSB
    x.reverse()
    x.insert(0, '1')  
    n = 0

    # Converting binary to integer
    for i in range(len(x)):  
        if x[i] == '1':
            n = n+math.pow(2, i)
    return int(n)

x = '01111'
print(Elias_Delta_Decoding(x))
```

**输出:**

```
7
```

**示例 2:** 生成对应于某个值的 Elias Delta 解码值的示例

## 计算机编程语言

```
import math

def  Elias_Delta_Decoding(x):
    x = list(x)
    L=0
    while True:
        if not x[L] == '0':
            break
        L= L + 1

    # Reading L more bits and dropping ALL
    x=x[2*L+1:] 

    # Prepending with 1 in MSB
    x.insert(0,'1') 
    x.reverse()
    n=0

    # Converting binary to integer
    for i in range(len(x)): 
        if x[i]=='1':
            n=n+math.pow(2,i)
    return int(n)

x = '0111100'
print(Elias_Delta_Decoding(x))
```

**输出:**

```
28
```