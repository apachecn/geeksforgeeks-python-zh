# Python 中的 Lambda 和 filter 示例

> 原文:[https://www . geesforgeks . org/lambda-filter-python-examples/](https://www.geeksforgeeks.org/lambda-filter-python-examples/)

前提条件:[Python 中的 Lambda](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

**给定一个数字列表，找出所有能被 13 整除的数字。**

```
Input : my_list = [12, 65, 54, 39, 102, 
                     339, 221, 50, 70]
Output : [65, 39, 221]

```

我们可以使用 filter()内置函数内部的 [Lambda](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/) 函数来查找列表中所有可被 13 整除的数字。在 Python 中，匿名函数意味着函数没有名称。

Python 中的 filter()函数接受一个函数和一个列表作为参数。这提供了一种优雅的方法来过滤掉序列“sequence”的所有元素，对于该序列，函数返回 True。

```
# Python Program to find numbers divisible 
# by thirteen from a list using anonymous 
# function

# Take a list of numbers. 
my_list = [12, 65, 54, 39, 102, 339, 221, 50, 70, ]

# use anonymous function to filter and comparing 
# if divisible or not
result = list(filter(lambda x: (x % 13 == 0), my_list)) 

# printing the result
print(result) 
```

输出:

```
[65, 39, 221]

```

**给定一个字符串列表，找到所有回文。**

```
# Python Program to find palindromes in 
# a list of strings.

my_list = ["geeks", "geeg", "keek", "practice", "aa"]

# use anonymous function to filter palindromes.
# Please refer below article for details of reversed
# https://www.geeksforgeeks.org/reverse-string-python-5-different-ways/
result = list(filter(lambda x: (x == "".join(reversed(x))), my_list)) 

# printing the result
print(result) 
```

输出:

```
['geeg', 'keek', 'aa']

```

**给定一个字符串列表和一个字符串，打印字符串的所有字谜**

```
# Python Program to find all anagrams of str in 
# a list of strings.
from collections import Counter

my_list = ["geeks", "geeg", "keegs", "practice", "aa"]
str = "eegsk"

# use anonymous function to filter anagrams of x.
# Please refer below article for details of reversed
# https://www.geeksforgeeks.org/anagram-checking-python-collections-counter/
result = list(filter(lambda x: (Counter(str) == Counter(x)), my_list)) 

# printing the result
print(result) 
```

输出:

```
['geeks', 'keegs']

```