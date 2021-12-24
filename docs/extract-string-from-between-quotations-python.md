# 从报价之间提取字符串–Python

> 原文:[https://www . geesforgeks . org/extract-string-from-inter-quotes-python/](https://www.geeksforgeeks.org/extract-string-from-between-quotations-python/)

在本文中，我们将学习如何使用 Python 在引用之间提取字符串。

**方法 1:**

要提取引文之间的字符串，我们可以使用 **re** 库中的 [findall()](https://www.geeksforgeeks.org/python-regex-re-search-vs-re-findall/) 方法。

## 蟒蛇 3

```
import re
inputstring = ' some strings are present in between "geeks" "for" "geeks" '

print(re.findall('"([^"]*)"', inputstring))
```

**输出:**

```
['geeks', 'for', 'geeks']
```

**方法二:**

我们可以使用 [split()](https://www.geeksforgeeks.org/python-string-split/) 方法和切片来提取报价之间的字符串。

## 蟒 3

```
inputstring = 'some strings are present in between "geeks" "for" "geeks" '

"""
here split() method will split the string for every quotation ( " ) .i.e.
['some strings are present in between ', 'geeks', ' ', 'for', ' ', 'geeks', ' ']. 

Then we will be storing all the strings at odd index.

"""

result = inputstring.split('"')[1::2]
print(result);
```

**输出:**

```
['geeks', 'for', 'geeks']
```

在这里可以了解更多关于 python 中[正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)和[列表切片](https://www.geeksforgeeks.org/python-list-slicing/)的内容。