# 找出给定范围内的所有 co 二进制数。

> 原文:[https://www . geesforgeks . org/find-all-the-co-the-binary-numbers-in-the-给定范围/](https://www.geeksforgeeks.org/find-all-the-co-binary-numbers-in-the-given-range/)

求 m 和 n 之间存在的共二进制回文的个数，共二进制回文是十进制数及其二进制转换都是回文的数。

**例:**

```
Input: starting number : 300, last number: 315

Output : 313

```

**代码:Python 代码查找给定范围内的所有 co 二进制数**

```
# Python code for co-binary palindromes

def convert_into_binary(number):
    return bin(number).replace("0b","")

def reverse_it(number):
    number = str(number)
    return number[::-1]

def is_palindrome(number):
    if number == int(reverse_it(number)) :
        return True
    else:
        return False

# starting number
m = 300

# ending number
n = 1000
bin_pals = []

for i in range(m,n+1):
    if is_palindrome(i) == True and is_palindrome(
            int(convert_into_binary(i))):

        bin_pals.append(i)

print(bin_pals)
```

**输出:**

```
[313, 585, 717]

```