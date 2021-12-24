# python 中的二进制到十进制，反之亦然

> 原文:[https://www . geesforgeks . org/binary-decimal-反之亦然-python/](https://www.geeksforgeeks.org/binary-decimal-vice-versa-python/)

编写 Python 代码，将十进制数转换为等效的二进制数，反之亦然。

**示例:**

```py
From decimal to binary
Input : 8
Output : 1 0 0 0

From binary to decimal
Input : 100
Output : 4
```

**十进制到二进制**

```py
Keep calling conversion function with n/2  till n > 1,
later perform n % 1 to get MSB of converted binary number.  
Example :- 7
1). 7/2 = Quotient = 3(greater than 1), Remainder = 1.
2). 3/2 = Quotient = 1(not greater than 1), Remainder = 1.
3). 1%2 = Remainder = 1.
Therefore, answer is 111.
```

## 蟒蛇 3

```py
# Function to print binary number for the
# input decimal using recursion
def decimalToBinary(n):

    if(n > 1):
        # divide with integral result
        # (discard remainder)
        decimalToBinary(n//2)

    print(n%2, end=' ')

# Driver code
if __name__ == '__main__':
    decimalToBinary(8)
    print("\n")
    decimalToBinary(18)
    print("\n")
    decimalToBinary(7)
    print("\n")
```

输出:

```py
1 0 0 0 
1 0 0 1 0 
1 1 1 
```

**使用 bin()将十进制转换为二进制:**

## 蟒蛇 3

```py
# Function to convert Decimal number
# to Binary number

def decimalToBinary(n):
    return bin(n).replace("0b","")

# Driver code
if __name__ == '__main__':
    print(decimalToBinary(8))
    print(decimalToBinary(18))
    print(decimalToBinary(7))
```

输出:

```py
1000
10010
111
```

**二进制到十进制**

```py
Example -: 1011
1). Take modulo of given binary number with 10\. 
    (1011 % 10 = 1)
2). Multiply rem with 2 raised to the power
    it's position from right end. 
    (1 * 2^0)
    Note that we start counting position with 0\. 
3). Add result with previously generated result.
    decimal = decimal + (1 * 2^0)
4). Update binary number by dividing it by 10.
    (1011 / 10 = 101)
5). Keep repeating upper steps till binary > 0.

Final Conversion -: (1 * 2^3) + (0 * 2^2) +
                 (1 * 2^1) + (1 * 2^0) = 11
```

## 蟒蛇 3

```py
# Function calculates the decimal equivalent
# to given binary number

def binaryToDecimal(binary):

    binary1 = binary
    decimal, i, n = 0, 0, 0
    while(binary != 0):
        dec = binary % 10
        decimal = decimal + dec * pow(2, i)
        binary = binary//10
        i += 1
    print(decimal)   

# Driver code
if __name__ == '__main__':
    binaryToDecimal(100)
    binaryToDecimal(101)
    binaryToDecimal(1001)
```

输出:

```py
4
5
9
```

**使用 int()将二进制转换为十进制:**

## 蟒蛇 3

```py
# Function to convert Binary number
# to Decimal number

def binaryToDecimal(n):
    return int(n,2)

# Driver code
if __name__ == '__main__':
    print(binaryToDecimal('100'))
    print(binaryToDecimal('101'))
    print(binaryToDecimal('1001'))
```

输出:

```py
4
5
9
```

本文由 **Pushpanjali Chauhan** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。