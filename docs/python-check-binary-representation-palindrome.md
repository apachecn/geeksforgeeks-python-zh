# 检查 Python 中二进制表示是否为回文

> 原文:[https://www . geesforgeks . org/python-check-binary-表象-回文/](https://www.geeksforgeeks.org/python-check-binary-representation-palindrome/)

给定一个整数“n”，编写一个 Python 函数，如果 x 的二进制表示是回文，则返回 true，否则返回 false。

示例:

```
Input : n = 9
Output : True
Binary representation of n=9 is 1001 which 
is palindrome as well.

Input : n = 10
Output : False
Binary representation of n=10 is 1010 which 
is not palindrome.

```

这个问题我们已经有了解决方案，请参考[检查一个数字的二进制表示是否是回文](https://www.geeksforgeeks.org/check-binary-representation-number-palindrome/)链接。我们可以用 python 非常快速地解决这个问题。方法很简单，

1.  Use the [bin (num)](https://www.geeksforgeeks.org/bin-in-python/) function to convert a given number into its binary representation.
2.  Now invert the binary representation string of numbers and compare it with the original binary representation string. If the two are equal, the binary representation of numbers is pallindrome, otherwise it is not.

**<u>注:</u>** 我们可以用[的其他方法检查一个字符串是不是回文](https://www.geeksforgeeks.org/c-program-check-given-string-palindrome/)。

```
# Function to check if binary representation of
# a number is pallindrome or not

def binaryPallindrome(num):

     # convert number into binary
     binary = bin(num)

     # skip first two characters of string
     # because bin function appends '0b' as 
     # prefix in binary representation of
     # a number
     binary = binary[2:]

     # now reverse binary string and compare
     # it with original
     return binary == binary[-1::-1]

# Driver program
if __name__ == "__main__":
    num = 9
    print binaryPallindrome(num)
```

输出:

```
True

```