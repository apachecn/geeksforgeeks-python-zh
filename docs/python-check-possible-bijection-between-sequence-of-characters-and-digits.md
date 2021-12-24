# Python |检查字符序列和数字之间可能的双射

> 原文:[https://www . geesforgeks . org/python-check-可能-字符和数字序列之间的双喷射/](https://www.geeksforgeeks.org/python-check-possible-bijection-between-sequence-of-characters-and-digits/)

给定一个字符串“char_seq”(字符序列)和一个正整数“dig_seq”(数字序列)，编写一个 Python 程序来寻找“char_seq”和“dig_seq”之间可能的双射或一对一的关系，使得每个字符只匹配一个数字。

**示例:**

```
Input : char_seq = 'bxdyxb'
        dig_seq = 123421
Output : True

Input : char_seq = 'bxdyxb'
        dig_seq = 123321
Output : False

```

**方法#1 :** 使用 *zip* 方法

这个方法只是将“char_seq”和“dig_seq”压缩，并检查相应的数字和字符是否匹配。

```
# Python3 program to Check possible bijection 
# between sequence of characters and digits

def is_bijection(char_seq, dig_seq):
    z = zip(str(char_seq), str(dig_seq))
    res = all(
    (z1[0] == z2[0]) == (z1[1] == z2[1]) for z1 in z for z2 in z)

    return res

# Driver code
char_seq = 'bxdyxb'
dig_seq = 123421
print(is_bijection(char_seq, dig_seq))
```

**Output:**

```
True

```

**方法 2 :** 使用 *itertools.groupby* 方法

这个方法使用相同的方法，只是略有不同，它使用 *itertools.groupby* 将字符与数字进行匹配。

```
# Python3 program to Check possible bijection 
# between sequence of characters and digits
import itertools

def is_bijection(char_seq, dig_seq):
    z = sorted(zip(str(char_seq), str(dig_seq)))
    res = all(gx == gy
          for k, g in itertools.groupby(z, key = lambda res: res[0])
          for gx in g for gy in g)

    return res

# Driver code
char_seq = 'bxdyxb'
dig_seq = 123421
print(is_bijection(char_seq, dig_seq))
```

**Output:**

```
True

```