# 使用 Python 中的正则表达式找到字符串中的所有数字

> 原文:[https://www . geeksforgeeks . org/使用 python 正则表达式查找字符串中的所有数字/](https://www.geeksforgeeks.org/find-all-the-numbers-in-a-string-using-regular-expression-in-python/)

给定一个包含数字和字母的字符串 **str** ，任务是使用正则表达式找到 **str** 中的所有数字。

**示例:**

> **输入:**ABCD 11 GDF 15 hnnnn 678 hh4
> **输出:** 11 15 678 4
> 
> **输入:**1 BCD 133 HHE 0
> T3】输出: 1 133 0

**方法:**思路是使用 [Python re](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/) 库从给定字符串中提取出与模式**【0-9】+**匹配的子字符串。该模式将提取从 **0** 到 **9** 匹配的所有字符， **+** 符号表示连续字符的一个或多个出现。

下面是上述方法的实现:

```
# Python3 program to extract all the numbers from a string
import re

# Function to extract all the numbers from the given string
def getNumbers(str):
    array = re.findall(r'[0-9]+', str)
    return array

# Driver code
str = "adbv345hj43hvb42"
array = getNumbers(str)
print(*array)
```

**Output:**

```
345 43 42

```