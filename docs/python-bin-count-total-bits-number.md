# Python Bin |计算数字中的总位数

> 原文:[https://www . geesforgeks . org/python-bin-count-total-bits-number/](https://www.geeksforgeeks.org/python-bin-count-total-bits-number/)

给定一个正数 n，计算其中的总位数。

**例:**

```py
Input : 13
Output : 4
Binary representation of 13 is 1101

Input  : 183
Output : 8

Input  : 4096
Output : 13

```

对于这个问题，我们已经有了解决方案，请参考[计算一个数字](https://www.geeksforgeeks.org/count-total-bits-number/)链接中的总位数。我们可以使用 [bin()](https://www.geeksforgeeks.org/bin-in-python/) 函数在 Python 中快速解决这个问题。使用 **bin()** 函数将数字转换为二进制，并删除输出二进制字符串的开头两个字符“0b”，因为 bin 函数在输出字符串中追加“0b”作为前缀。现在打印二进制字符串的长度，它是输入数字的二进制表示的位数。

## 蟒蛇 3

```py
# Function to count total bits in a number

def countTotalBits(num):

     # convert number into it's binary and
     # remove first two characters 0b.
     binary = bin(num)[2:]
     print(len(binary))

# Driver program
if __name__ == "__main__":
    num = 13
    countTotalBits(num)
```

**输出:**

```py
4

```