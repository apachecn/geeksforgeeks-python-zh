# Python |检查给定的字符串是否可以通过串联列表的字符串元素形成

> 原文:[https://www . geeksforgeeks . org/python-检查给定字符串是否可以通过串联列表中的字符串元素来形成/](https://www.geeksforgeeks.org/python-check-if-given-string-can-be-formed-by-concatenating-string-elements-of-list/)

给定一个字符串“str”和一个字符串元素列表，编写一个 Python 程序来检查给定的字符串是否可以通过串联列表的字符串元素来形成。

**示例:**

```py
Input : str = 'python'
        lst = ['co', 'de', 'py', 'ks', 'on']
Output : False

Input : str = 'geeks'
        lst = ['for', 'ge', 'abc', 'ks', 'e', 'xyz']
Output : True
```

**方法#1 :** 使用 itertools .置换

我们可以使用给定列表的所有排列，然后对它们执行*连接*操作。如果任何联接结果等于给定的字符串，则返回 true，否则返回 false。

## 蟒蛇 3

```py
# Python3 program to Check if given string can
# be formed by concatenating string elements
# of list
from itertools import permutations

def checkList(str, lst):
    for i in range(2, len(lst)+1):
        for perm in permutations(lst, i):
            if ''.join(perm)== str:
                return True

    return False

# Driver code
str = 'geeks'
lst = ['for', 'ge', 'abc', 'ks', 'e', 'xyz']
print(checkList(str, lst))
```

**Output:** 

```py
True
```

**进场#2 :** 蟒蛇*雷杰克斯*

## 蟒蛇 3

```py
# Python3 program to Check if given string can
# be formed by concatenating string elements
# of list
import re

def checkList(str, lst):

    r = re.compile("(?:" + "|".join(lst) + ")*{content}quot;)
    if r.match(str) != None:
        return True

    return False

# Driver code
str = 'geeks'
lst = ['for', 'ge', 'abc', 'ks', 'e']
print(checkList(str, lst))
```

**Output:** 

```py
True
```