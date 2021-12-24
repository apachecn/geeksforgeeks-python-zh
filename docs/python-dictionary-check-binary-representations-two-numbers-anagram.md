# Python 字典|检查两个数字的二进制表示是否是字谜

> 原文:[https://www . geesforgeks . org/python-dictionary-check-binary-表象-二进制-数字-字谜/](https://www.geeksforgeeks.org/python-dictionary-check-binary-representations-two-numbers-anagram/)

给定两个数字，你需要检查它们在二进制表示中是否是彼此的字谜。

示例:

```py
Input : a = 8, b = 4 
Output : Yes
Binary representations of both
numbers have same 0s and 1s.

Input : a = 4, b = 5
Output : No

```

这个问题我们已经有了解决方案，请参考[检查两个数字的二进制表示是否是字谜](https://www.geeksforgeeks.org/check-binary-representations-two-numbers-anagram/)链接。我们可以使用[计数器(可迭代)](https://www.geeksforgeeks.org/counters-in-python-set-1/)方法和**字典比较**在 python 中快速解决这个问题。方法很简单，

1.  使用 [bin()](https://www.geeksforgeeks.org/bin-in-python/) 函数将两个数字都转换为二进制。
2.  由于两个数字的二进制表示长度可能不同，因此我们将在较短字符串的开头添加零，使两个字符串的长度相等。ie。；追加零= abs(len(bin1)-len(bin2))。
3.  使用 **Counter()** 函数，将 bin 函数返回的包含 0 和 1 的输出字符串转换为字典，0 和 1 键及其计数作为值。比较两个字典，如果两个字典中 0 和 1 的值相等，则两个数字的二进制表示是字谜，否则不是。

```py
# function to Check if binary representations
# of two numbers are anagram
from collections import Counter

def checkAnagram(num1,num2):

    # convert numbers into in binary
    # and remove first two characters of 
    # output string because bin function 
    # '0b' as prefix in output string
    bin1 = bin(num1)[2:]
    bin2 = bin(num2)[2:]

    # append zeros in shorter string
    zeros = abs(len(bin1)-len(bin2))
    if (len(bin1)>len(bin2)):
         bin2 = zeros * '0' + bin2
    else:
         bin1 = zeros * '0' + bin1

    # convert binary representations 
    # into dictionary
    dict1 = Counter(bin1)
    dict2 = Counter(bin2)

    # compare both dictionaries
    if dict1 == dict2:
         print('Yes')
    else:
         print('No')

# Driver program
if __name__ == "__main__":
    num1 = 8
    num2 = 4
    checkAnagram(num1,num2)

```

输出:

```py
Yes

```