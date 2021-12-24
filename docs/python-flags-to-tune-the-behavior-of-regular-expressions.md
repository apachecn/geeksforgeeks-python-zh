# Python 标记调整正则表达式的行为

> 原文:[https://www . geesforgeks . org/python-flags-to-tune-behavior-of-behavior-of-正则表达式/](https://www.geeksforgeeks.org/python-flags-to-tune-the-behavior-of-regular-expressions/)

Python 提供了一些标志来修改正则表达式引擎的行为。下面我们来讨论一下:

1.  Not case-sensitive
2.  Point matching newline character
3.  Multi-line mode
4.  Detailed mode
5.  Debugging mode

## 案件不敏感

戒指。IGNORECASE 允许正则表达式变得不区分大小写。这里，匹配是基于所提供字符串的大小写返回的，而不是正则表达式中的字符串。

## 蟒 3

```py
import re

match = re.search(r'geeksforgeeks', 'GeeksforGeeks',re.IGNORECASE)
print(match)
```

**输出**

```py
<_sre.SRE_Match object; span=(0, 13), match='GeeksforGeeks'>

```