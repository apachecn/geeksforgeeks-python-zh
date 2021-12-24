# Python–b = 2n 和 b 的 Golomb 编码！=2n

> 原文:[https://www . geesforgeks . org/python-golomb-encoding-for-b2n-and-b2n/](https://www.geeksforgeeks.org/python-golomb-encoding-for-b2n-and-b2n/)

Golomb 编码是参数化编码的一种形式，其中要编码的整数被存储为相对于常数 b 的值

**编码:-**
正数 x 分为两部分:

*   初始段是 q+1 的一元描述，其中 q 是余数下限((x/b))，并且
*   接下来的部分是对剩余部分 **r = x-qb** 的非凡双重刻画。注意，有最好的潜在剩菜。

例如，如果 b = 3，潜在的余数将是 0、1 和 2。为了节省空间，利用地板(log(b，2))位组成最初的一对残余部分，利用天花板(log(b，2))位组成其余部分。我们这样做的最终目标应该是解码器知道何时使用了 floor(log(b，2))位，何时使用了 ceil(log(b，2))位

**示例:**

```
Input  : N = 37, M = 11 
Output : 0001100

```

**代码:实现 Golomb 编码的 Python 程序**

```
# Python programming for Golomb Encoding
import math

# taking input for N and  M where 
# M == 2 ^ n or M != 2 ^ n
N = 37
M = 11

# for finding the value of preceding 
# number of zeros by dividing N by M
q = N//M
# for computing the remainder of N by M
r = N % M

# appending that many numbers of zeros in
# starting of the encoded code initially 
quo ='0'*q+'1'

# for computing the value of b ie floor of 
# log(M) base 2 which will be used for computing value of k
b = math.floor(math.log2(M))
k = 2**(b + 1)-M
# upon comparing the value of remainder with the 
# value of k if less we we convert remainder r to 
# binary and add the value from # index 2 because 
# at index 0, 1 "0b" is present
if r < k:
    rem = bin(r)[2:]
    l = len(rem)

# upon the calculating value of rem if it is less than
# computed value of b we add b-1 number of zeros in
# preceding of the # remainder
    if l<b:
        rem = '0'*(b-l)+rem
else:
# we convert remainder r to binary and add the 
# value from index 2 because at index 0, 1 "0b" is present
    rem = bin(r + k)[2:]
    l = len(rem)
# upon calculating value of rem if it is less than
# computed value of b we add b-1 number of zeros in
# preceding of the # remainder
    if l<b + 1:
        rem = '0'*(b + 1-l)+rem
golomb_code = quo + rem
print("The golomb code encoding for x = {} and b = {} is {}".
      format(N, M, golomb_code))
```

**输出:**

```
The golomb code encoding for x = 37 and b = 11 is 0001100
```