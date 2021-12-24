# 用 Python 计算 n+nn+nnn+……+n(m 次)

> 原文:[https://www . geesforgeks . org/calculate-n-nn-nnn-nm-times-python/](https://www.geeksforgeeks.org/calculate-n-nn-nnn-nm-times-python/)

程序是找到一个数学级数，这里我们需要接受 n 和 m 的值，n 是基数，m 是级数运行的次数。

示例:

```
Input : 2 + 22 + 222 + 2222 + 22222 
Output : 24690

Input : 12 + 1212 + 121212
Output : 122436

```

我们首先将数字转换成字符串格式，并定期连接它们。稍后，我们将它们转换回整数，并将其加到第 m 项。如下图所示。

```
# Python program to sum the given series

# Returns sum of n + nn + nnn + .... (m times)
def Series(n, m):

    # Converting the number to string
    str_n = str(n)

    # Initializing result as number and string
    sums = n
    sum_str = str(n)

    # Adding remaining terms
    for i in range(1, m):

        # Concatenating the string making n, nn, nnn...
        sum_str = sum_str + str_n

        # Before adding converting back to integer
        sums = sums + int(sum_str)

    return sums

# Driver Code
n = 2
m = 5
total = Series(n, m)
print(total)
```

输出:

```
24690

```