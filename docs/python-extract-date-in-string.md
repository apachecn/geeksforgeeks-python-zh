# Python–提取字符串中的日期

> 原文:[https://www . geesforgeks . org/python-extract-date-in-string/](https://www.geeksforgeeks.org/python-extract-date-in-string/)

给定一个字符串，任务是编写一个 Python 程序从中提取日期。

```
Input : test_str = "gfg at 2021-01-04"
Output : 2021-01-04
Explanation : Date format string found.

Input : test_str = "2021-01-04 for gfg"
Output : 2021-01-04
Explanation : Date format string found.
```

**方法#1:使用** [**重新搜索()**](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/)**+str time()方法**

在这种情况下，特定日期的搜索组被输入到 search()中，而 strptime()用于以要搜索的格式输入。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Detect date in String
# Using re.search() + strptime()
import re
from datetime import datetime

# initializing string
test_str = "gfg at 2021-01-04"

# printing original string
print("The original string is : " + str(test_str))

# searching string
match_str = re.search(r'\d{4}-\d{2}-\d{2}', test_str)

# computed date
# feeding format
res = datetime.strptime(match_str.group(), '%Y-%m-%d').date()

# printing result
print("Computed date : " + str(res))
```

**输出:**

```
The original string is : gfg at 2021-01-04
Computed date : 2021-01-04
```

**方法 2:使用**[**python-datutil()**](https://www.geeksforgeeks.org/nlp-using-dateutil-to-parse-dates/)**模块**

这是解决这个问题的另一种方法。在这个内置的 Python 库 python-dateutil 中，parse()方法可以用来检测字符串中的日期和时间。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Detect date in String
# Using python-dateutil()
from dateutil import parser

# initializing string
test_str = "gfg at 2021-01-04"

# printing original string
print("The original string is : " + str(test_str))

# extracting date using inbuilt func.
res = parser.parse(test_str, fuzzy=True)

# printing result
print("Computed date : " + str(res)[:10])
```

**输出:**

```
The original string is : gfg at 2021-01-04
Computed date : 2021-01-04
```