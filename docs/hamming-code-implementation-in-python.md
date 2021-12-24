# Python 中的汉明码实现

> 原文:[https://www . geesforgeks . org/hamming-code-implementation-in-python/](https://www.geeksforgeeks.org/hamming-code-implementation-in-python/)

**先决条件:** [汉明码](https://www.geeksforgeeks.org/hamming-code-in-computer-network/)

[汉明码](https://www.geeksforgeeks.org/hamming-code-in-computer-network/)是一组纠错码，可用于检测和纠正数据从发送方移动或存储到接收方时可能出现的错误。这是一种由海明开发的纠错技术。

**步骤:**

1.  输入要传输的数据
2.  计算所需的冗余位数
3.  确定奇偶校验位
4.  为测试创建错误数据
5.  检查错误

**示例:**

```
Input: 
1011001

Output:
Data transferred is 10101001110
Error Data is 11101001110
The position of error is 10

Input:
10101111010

Output:
Data transferred is 101011111010000
Error Data is 101011111010100
The position of error is 3
```

## 蟒蛇 3

```
# Python program to demonstrate
# hamming code

def calcRedundantBits(m):

    # Use the formula 2 ^ r >= m + r + 1
    # to calculate the no of redundant bits.
    # Iterate over 0 .. m and return the value
    # that satisfies the equation

    for i in range(m):
        if(2**i >= m + i + 1):
            return i

def posRedundantBits(data, r):

    # Redundancy bits are placed at the positions
    # which correspond to the power of 2.
    j = 0
    k = 1
    m = len(data)
    res = ''

    # If position is power of 2 then insert '0'
    # Else append the data
    for i in range(1, m + r+1):
        if(i == 2**j):
            res = res + '0'
            j += 1
        else:
            res = res + data[-1 * k]
            k += 1

    # The result is reversed since positions are
    # counted backwards. (m + r+1 ... 1)
    return res[::-1]

def calcParityBits(arr, r):
    n = len(arr)

    # For finding rth parity bit, iterate over
    # 0 to r - 1
    for i in range(r):
        val = 0
        for j in range(1, n + 1):

            # If position has 1 in ith significant
            # position then Bitwise OR the array value
            # to find parity bit value.
            if(j & (2**i) == (2**i)):
                val = val ^ int(arr[-1 * j])
                # -1 * j is given since array is reversed

        # String Concatenation
        # (0 to n - 2^r) + parity bit + (n - 2^r + 1 to n)
        arr = arr[:n-(2**i)] + str(val) + arr[n-(2**i)+1:]
    return arr

def detectError(arr, nr):
    n = len(arr)
    res = 0

    # Calculate parity bits again
    for i in range(nr):
        val = 0
        for j in range(1, n + 1):
            if(j & (2**i) == (2**i)):
                val = val ^ int(arr[-1 * j])

        # Create a binary no by appending
        # parity bits together.

        res = res + val*(10**i)

    # Convert binary to decimal
    return int(str(res), 2)

# Enter the data to be transmitted
data = '1011001'

# Calculate the no of Redundant Bits Required
m = len(data)
r = calcRedundantBits(m)

# Determine the positions of Redundant Bits
arr = posRedundantBits(data, r)

# Determine the parity bits
arr = calcParityBits(arr, r)

# Data to be transferred
print("Data transferred is " + arr) 

# Stimulate error in transmission by changing
# a bit value.
# 10101001110 -> 11101001110, error in 10th position.

arr = '11101001110'
print("Error Data is " + arr)
correction = detectError(arr, r)
print("The position of error is " + str(correction))
```

**输出:**

```
Data transferred is 10101001110
Error Data is 11101001110
The position of error is 2
```