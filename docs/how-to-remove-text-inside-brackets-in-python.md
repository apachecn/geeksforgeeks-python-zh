# Python 中如何去掉括号内的文字？

> 原文:[https://www . geesforgeks . org/如何删除 python 括号内的文本/](https://www.geeksforgeeks.org/how-to-remove-text-inside-brackets-in-python/)

在本文中，我们将学习如何在 python 中移除括号内的内容而不移除括号。

**例:**

```
Input: (hai)geeks
Output: ()geeks

Input: (geeks)for(geeks)
Output: ()for()
```

我们可以在两种方法中删除括号内的内容而不删除括号，其中一种方法是使用 re 库中的内置方法，第二种方法是通过使用 for 循环迭代字符串来实现这一功能

**方法 1:** 我们将使用 re 库(正则表达式)的 sub()方法。

**sub():**sub()方法的功能是它会找到具体的模式，并用一些字符串来代替。

该方法将找到括号或括号中的子字符串，并用空括号替换它。

**方法:**

1.  Import re library
2.  Now find the substring in brackets and use the sub () method to replace it with **()** .
3.  We need to pass the sub () method with two parameters, namely **mode** and **string to be replaced with.**
4.  Print strings.

在下面的代码中 **\(。*?\)** 表示查找包含某些内容的括号的正则表达式。括号 **()** 在 python 的正则表达式中有一些特殊的含义，所以 Backlash **\** 用来逃避这个含义。

## python 3

```
# Importing module
import re

# Input string
string="(Geeks)for(Geeks)"

# \(.*?\) ==> it is a regular expression for finding
# the pattern for brackets containing some content
string=re.sub("\(.*?\)","()",string)

# Output string
print(string)
```

**输出**

```
()for()
```

**时间复杂度:** O(2^m + n)。

其中 m 是正则表达式的大小，n 是字符串的大小。这里 sub()方法将花费 2^m 时间使用正则表达式和 O(n)来遍历字符串并替换为**“()”来找到模式。**

**方法 2:** 在这个方法中，我们将遍历字符串，如果被迭代的字符不在括号之间，那么该字符将被添加到结果字符串中。

如果字符串中存在左括号或右括号，则括号将被添加到结果字符串中，但中间的字符串不会被添加到结果字符串中。

**方法:**

1.  Iterate the loop of each character in the string.
2.  If a **("** or **)"** appears in the string, we will add it to the result string.
3.  If the number of brackets in the string is zero, the character is added to the result string.
4.  Here, if the number of brackets is greater than zero, it means that the current character being iterated appears between two brackets.
5.  Print the result string.

## 蟒 3

```
# Input string
string="geeks(for)geeks"

# resultant string
result = ''

# paren counts the number of brackets encountered
paren= 0
for ch in string:

    # if the character is ( then increment the paren
    # and add ( to the resultant string.
    if ch == '(':
        paren =paren+ 1
        result = result + '('

    # if the character is ) and paren is greater than 0, 
    # then increment the paren and 
    # add ) to the resultant string.
    elif (ch == ')') and paren:
        result = result + ')'
        paren =paren- 1

    # if the character neither ( nor  then add it to
    # resultant string.
    elif not paren:
        result += ch

# print the resultant string.
print(result)
```

**输出**

```
geeks()geeks
```

**时间复杂度:** O(n)。

这里 n 是字符串的长度。在代码中，我们对字符串进行迭代，并将内容附加到括号外，这样只需要 O(n)时间。