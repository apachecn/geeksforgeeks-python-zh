# Python–不区分大小写的字符串替换

> 原文:[https://www . geesforgeks . org/python-不区分大小写-字符串替换/](https://www.geeksforgeeks.org/python-case-insensitive-string-replacement/)

给定一串单词。任务是编写一个 Python 程序，用给定的字符串替换给定的单词，而不考虑大小写。

**示例:**

> **输入:**test _ str =“gfg 为最佳”，repl =“良好”，subs =“最佳”
> 
> **输出:** gfg 良好
> 
> **解释:** BeSt 替换为“好”忽略案例。
> 
> **输入:** test_str = "gfg 为最佳"，repl = "better "，subs = "best "
> 
> **输出:** gfg 较好
> 
> **解释:** BeSt 替换为“better”忽略案例。

**方法#1:使用 re。IGNORECASE+re . escape()+re . sub()**

在这种情况下，regex 的 sub()用于执行替换和 IGNORECASE 的任务，忽略大小写并执行不区分大小写的替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Case insensitive Replace
# Using re.IGNORECASE + re.escape() + re.sub()
import re

# initializing string
test_str = "gfg is BeSt"

# printing original string
print("The original string is : " + str(test_str))

# initializing replace string 
repl = "good"

# initializing substring to be replaced 
subs = "best"

# re.IGNORECASE ignoring cases 
# compilation step to escape the word for all cases
compiled = re.compile(re.escape(subs), re.IGNORECASE)
res = compiled.sub(repl, test_str)

# printing result
print("Replaced String : " + str(res))
```

**Output**

```
The original string is : gfg is BeSt
Replaced String : gfg is good
```

**方法 2:使用 sub()+**[**lambda**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)**+escape()**

使用特殊的忽略格正则表达式也可以解决这个问题。Rest，lambda 函数用于处理字符串中的转义字符。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Case insensitive Replace
# Using sub() + lambda + escape() 
import re

# initializing string
test_str = "gfg is BeSt"

# printing original string
print("The original string is : " + str(test_str))

# initializing replace string 
repl = "good"

# initializing substring to be replaced 
subs = "best"

# regex used for ignoring cases
res = re.sub('(?i)'+re.escape(subs), lambda m: repl, test_str)

# printing result
print("Replaced String : " + str(res))
```

**Output**

```
The original string is : gfg is BeSt
Replaced String : gfg is good
```