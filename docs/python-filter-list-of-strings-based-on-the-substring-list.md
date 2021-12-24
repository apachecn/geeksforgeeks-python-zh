# Python |基于子字符串列表过滤字符串列表

> 原文:[https://www . geesforgeks . org/python-filter-list-基于字符串的子字符串列表/](https://www.geeksforgeeks.org/python-filter-list-of-strings-based-on-the-substring-list/)

给定两个字符串列表*字符串*和*子字符串*，编写一个 Python 程序过滤掉*字符串*中包含*子字符串*中字符串的所有字符串。

**示例:**

```py
Input : string = ['city1', 'class5', 'room2', 'city2']
        substr = ['class', 'city']
Output : ['city1', 'class5', 'city2']

Input : string = ['coordinates', 'xyCoord', '123abc']
        substr = ['abc', 'xy']
Output : ['xyCoord', '123abc']

```

**方法#1 :** 使用列表理解

我们可以在运算符中使用列表理解和*来检查“substr”中的字符串是否包含在“string”中。*

```py
# Python3 program to Filter list of 
# strings based on another list
import re

def Filter(string, substr):
    return [str for str in string if
             any(sub in str for sub in substr)]

# Driver code
string = ['city1', 'class5', 'room2', 'city2']
substr = ['class', 'city']
print(Filter(string, substr))
```

**Output:**

```py
['city1', 'class5', 'city2']

```

**方法 2 :** Python 正则表达式

```py
# Python3 program to Filter list of 
# strings based on another list
import re

def Filter(string, substr):
    return [str for str in string 
    if re.match(r'[^\d]+|^', str).group(0) in substr]

# Driver code
string = ['city1', 'class5', 'room2', 'city2']
substr = ['class', 'city']
print(Filter(string, substr))
```

**Output:**

```py
['city1', 'class5', 'city2']

```