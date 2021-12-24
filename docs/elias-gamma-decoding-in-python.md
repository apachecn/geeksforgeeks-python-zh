# Python 中 Elias Gamma 解码

> 原文:[https://www . geesforgeks . org/Elias-gamma-python 解码/](https://www.geeksforgeeks.org/elias-gamma-decoding-in-python/)

Elias gamma 码是一种通用码，用于对正整数序列进行编码。它是由彼得·埃利亚斯开发的。当不能事先确定整数的上限时，这是最有用的。

**公式:**

> Elias Gamma 编码=一元(1+地板(log2(x)))+不带 MSB 的“x”的二进制表示

**示例**:我们考虑一个要解码 0001001 的示例，

```
Apply Step 1:
Count the number of '0's from MSB until you reach the first '1' and store the count in K.
In our example(0001001) K=3 

Apply Step 2:
Read 3 more bits including the first '1'=1001

Apply Step 3:
Convert the final binary into integer which gives us the original number.
Decimal(1001)=9
```

## 分步**实施**

**第 1 步:**从 MSB 开始计数‘0’的数量，直到到达第一个‘1’，并将计数存储在 k 中

## 蟒蛇 3

```
# define the function
def Elias_Gamma_Decoding(x):

    # convert to list
    x = list(x)

    # initialize k to 0
    K = 0
    while True:

        # check if k is not 0 in through
        # list index
        if not x[K] == '0':
            break

        # increment k value
        K = K + 1
```

**步骤 2:** 将“1”视为第一位数字，并从当前“1”中多读取“K”位

## 蟒蛇 3

```
x = x[K:2*K+1]  # Reading K more bits from '1'
```

**第三步:**将最终的二进制数转换成整数，得到原始的数。

## 蟒蛇 3

```
# Converting binary to integer
for i in range(len(x)):
    if x[i] == '1':
        n = n+math.pow(2, i)
return int(n)
```

下面是上述方法的完整实现。

## 蟒蛇 3

```
# import the math module
import math

# function
def Elias_Gamma_Decoding(x):
    x = list(x)
    K = 0
    while True:
        if not x[K] == '0':
            break
        K = K + 1

    # Reading K more bits from '1'
    x = x[K:2*K+1]

    n = 0
    x.reverse()

    # Converting binary to integer
    for i in range(len(x)):
        if x[i] == '1':
            n = n+math.pow(2, i)
    return int(n)

# value input
x = '0001001'

# call the function
print(Elias_Gamma_Decoding(x))
```

**输出:**

```
9
```