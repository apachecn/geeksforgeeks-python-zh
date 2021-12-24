# Python–使用正则表达式

检查字符串是否只包含定义的字符

> 原文:[https://www . geesforgeks . org/python-check-if-string-contain-only-defined-characters-use-regex/](https://www.geeksforgeeks.org/python-check-if-string-contain-only-defined-characters-using-regex/)

在本文中，我们将看到如何在 Python 中检查给定的字符串是否只包含特定的字符集。这些定义的字符将使用集合来表示。

**示例:**

> **输入:**‘657’假设正则表达式包含以下字符-
> (【78653】)
> **输出:**有效 **解释:**输入字符串仅由给定字符串中的字符组成
> 
> **输入:**‘7606’假设正则表达式包含以下字符-
> (【102】)
> **输出:**无效

**进场:**

方法很简单，我们将使用正则表达式定义字符集。正则表达式是一种特殊的字符模式或序列，允许我们匹配和查找其他字符集或字符串。

**使用的功能:**

*   **compile():** 正则表达式被编译成模式对象，这些对象具有用于各种操作的方法，例如搜索模式匹配或执行字符串替换。
*   **search():**re . search()方法要么返回 None(如果模式不匹配)，要么返回一个 re。MatchObject 包含字符串匹配部分的信息。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。

下面是实现。

## 蟒蛇 3

```
# _importing module
import re

def check(str, pattern):

    # _matching the strings
    if re.search(pattern, str):
        print("Valid String")
    else:
        print("Invalid String")

# _driver code
pattern = re.compile('^[1234]+{content}apos;)
check('2134', pattern)
check('349', pattern)
```

**输出:**

```
Valid String
Invalid String

```