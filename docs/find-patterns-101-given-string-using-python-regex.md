# 使用 Python Regex

查找给定字符串中“1(0+)1”的所有模式

> 原文:[https://www . geesforgeks . org/find-patterns-101-给定-字符串-使用-python-regex/](https://www.geeksforgeeks.org/find-patterns-101-given-string-using-python-regex/)

字符串包含 1(0+)1 形式的模式，其中(0+)表示任何非空的连续 0 序列。请统计所有此类模式。允许图案重叠。

**注意:**只包含数字和小写字符。字符串不一定是二进制的。100201 不是有效的模式。

示例:

```
Input : 1101001
Output : 2

Input : 100001abc101
Output : 2

```

这个问题我们已经有了解决方案，请参考[找到给定字符串](https://www.geeksforgeeks.org/find-patterns-101-given-string/)链接中“1(0+)1”的所有模式。另一套包含类似的解决方案[使用正则表达式在 java 中](https://www.geeksforgeeks.org/find-patterns-101-given-string-set-2regular-expression-approach/)也出版了。

我们将使用 [Regex](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/) 在 python 中快速解决这个问题。方法很简单:

1.  使用 [re.search(regex，string)](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/) 方法搜索遵循“10+1”模式的原始字符串中的第一个子字符串。
2.  **substr = re.search(regex，string)** 如果在原始字符串中没有找到给定的 regex 作为子字符串，则返回 **None** ，否则返回遵循“10+1”模式的第一个匹配的子字符串。 **substr.start()** 给出匹配正则表达式的起始索引， **substr.end()** 给出匹配正则表达式的结束索引。
3.  每当我们发现正则表达式是子串时，就将计数增加 1，并从前一个子串的结束索引开始再次搜索给定的正则表达式。

```
# Python program to Find all the patterns 
# of “1(0+)1” in a given string using Python Regex

import re

# Function to Find all the patterns
# of “1(0+)1” in a given string
def extract(input):

    # search regex '10+1' in original string
    # search() function return first occurrence 
    # of regex '10+1' otherwise None
    # '10+1' means sub-string starting and ending with 1
    # and atleast 1 or more zeros in between
    count=0
    substr = re.search('10+1',input)

    # search for regex in original string 
    # untill we are done with complete string
    while substr!=None:
        # if we find any occurrence then increase count by 1
        count=count+1

        # find next occurrence just after previous 
        # sub-string
        # for first occurrence 101, substr.start()=1
        # substr.end()=4
        input = input[(substr.end()-1):]
        substr = re.search('10+1',input)
    print (count)

# Driver program
if __name__ == "__main__":
    input = '1101001'
    extract(input)
```

输出:

```
2

```