# Python |从给定字符串中提取单词

> 原文:[https://www . geesforgeks . org/python-extract-words-from-given-string/](https://www.geeksforgeeks.org/python-extract-words-from-given-string/)

我们有时会遇到需要获取字符串中所有单词的情况，这可能是一项使用本机方法完成的乏味任务。因此，让人手不足的人来执行这项任务总是有用的。此外，本文还包括标点符号必须被忽略的情况。
**方法#1:使用 split()**
使用 split 函数，我们可以将字符串拆分成单词列表，如果想要完成这个特定的任务，这是最通用和推荐的方法。但缺点是，如果字符串包含标点符号，它会失败。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to extract words from string
# using split()

# initializing string 
test_string = "Geeksforgeeks is best Computer Science Portal"

# printing original string
print ("The original string is : " +  test_string)

# using split()
# to extract words from string
res = test_string.split()

# printing result
print ("The list of words is : " +  str(res))
```

**Output:** The original string is : Geeksforgeeks is best Computer Science Portal The list of words is : [‘Geeksforgeeks’, ‘is’, ‘best’, ‘Computer’, ‘Science’, ‘Portal’]  

**方法#2:使用正则表达式(findall() )**
在包含所有特殊字符和标点符号的情况下，如上所述，使用 split 在字符串中查找单词的传统方法可能会失败，因此需要正则表达式来执行此任务。findall 函数在过滤字符串并提取忽略标点符号的单词后返回列表。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to extract words from string
# using regex( findall() )
import re

# initializing string 
test_string = "Geeksforgeeks,    is best @# Computer Science Portal.!!!"

# printing original string
print ("The original string is : " +  test_string)

# using regex( findall() )
# to extract words from string
res = re.findall(r'\w+', test_string)

# printing result
print ("The list of words is : " +  str(res))
```

**Output:** The original string is : Geeksforgeeks, is best @# Computer Science Portal.!!! The list of words is : [‘Geeksforgeeks’, ‘is’, ‘best’, ‘Computer’, ‘Science’, ‘Portal’]  

**方法三:使用 regex() + string .标点符号**
该方法也使用了正则表达式，但是使用了获取所有标点符号的 string 函数，忽略所有标点符号，得到过滤后的结果字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to extract words from string
# using regex() + string.punctuation
import re
import string

# initializing string 
test_string = "Geeksforgeeks,    is best @# Computer Science Portal.!!!"

# printing original string
print ("The original string is : " +  test_string)

# using regex() + string.punctuation
# to extract words from string
res = re.sub('['+string.punctuation+']', '', test_string).split()

# printing result
print ("The list of words is : " +  str(res))
```

**Output:** The original string is : Geeksforgeeks, is best @# Computer Science Portal.!!! The list of words is : [‘Geeksforgeeks’, ‘is’, ‘best’, ‘Computer’, ‘Science’, ‘Portal’]