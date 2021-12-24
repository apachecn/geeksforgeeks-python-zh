# Python |检查字符串中的网址

> 原文:[https://www.geeksforgeeks.org/python-check-url-string/](https://www.geeksforgeeks.org/python-check-url-string/)

**前提:** [正则表达式模式匹配](https://www.geeksforgeeks.org/pattern-matching-python-regex/)

在本文中，我们将需要接受一个字符串，并且我们需要检查该字符串中是否包含任何网址。如果网址出现在字符串中，我们会说网址已经找到或没有，并打印相应的网址出现在字符串中。我们将使用 Python 正则表达式的概念来解决这个问题。

示例:

```
Input : string = 'My Profile: 
https://auth.geeksforgeeks.org/user/Chinmoy%20Lenka/articles 
in the portal of https://www.geeksforgeeks.org/'

Output : URLs :  ['https://auth.geeksforgeeks.org/user/Chinmoy%20Lenka/articles',
'https://www.geeksforgeeks.org/']

Input : string = 'I am a blogger at https://geeksforgeeks.org'
Output : URL :  ['https://geeksforgeeks.org']

```

为了找到给定字符串中的网址，我们使用了 Python 的[正则表达式模块中的](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/) [findall()](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/) 函数。这将返回字符串中所有不重叠模式匹配，作为字符串列表。从左到右扫描字符串，并按照找到的顺序返回匹配项。

```
# Python code to find the URL from an input string
# Using the regular expression
import re

def Find(string):

    # findall() has been used 
    # with valid conditions for urls in string
    regex = r"(?i)\b((?:https?://|www\d{0,3}[.]|[a-z0-9.\-]+[.][a-z]{2,4}/)(?:[^\s()<>]+|\(([^\s()<>]+|(\([^\s()<>]+\)))*\))+(?:\(([^\s()<>]+|(\([^\s()<>]+\)))*\)|[^\s`!()\[\]{};:'\".,<>?«»“”‘’]))"
    url = re.findall(regex,string)      
    return [x[0] for x in url]

# Driver Code
string = 'My Profile: https://auth.geeksforgeeks.org/user/Chinmoy%20Lenka/articles in the portal of https://www.geeksforgeeks.org/'
print("Urls: ", Find(string))
```

输出:

```
Urls:  ['https://auth.geeksforgeeks.org/user/Chinmoy%20Lenka/articles',
'https://www.geeksforgeeks.org/']

```