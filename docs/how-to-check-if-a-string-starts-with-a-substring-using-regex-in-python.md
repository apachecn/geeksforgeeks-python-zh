# 如何用 Python 中的正则表达式检查字符串是否以子字符串开头？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 中的-regex 检查字符串是否以子字符串开头/](https://www.geeksforgeeks.org/how-to-check-if-a-string-starts-with-a-substring-using-regex-in-python/)

**先决条件:**[Python 中的正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

给定一个字符串 **str，**的任务是检查一个字符串是否以给定的子字符串开始或者没有使用正则表达式。

**示例:**

```py
Input: String: "geeks for geeks makes learning fun" 
       Substring: "geeks" 
Output: True 
Input: String: "geeks for geeks makes learning fun" 
       Substring: "makes" 
Output: False
```

**方法 1:**
这里，我们首先检查字符串中是否存在给定的子字符串。如果是，那么我们使用 **re library** 的 **search()** 函数以及元字符**“^".**这个元字符检查给定的字符串是否从提供的子字符串开始。

下面是上述方法的实现:

## 蟒蛇 3

```py
# import library
import re

# define a function 
def find(string, sample) :

  # check substring present 
  # in a string or not
  if (sample in string):

      y = "^" + sample

      # check if string starts 
      # with the substring
      x = re.search(y, string)

      if x :
          print("string starts with the given substring")

      else :
          print("string doesn't start with the given substring")

  else :
      print("entered string isn't a substring")

# Driver code
string = "geeks for geeks makes learning fun"  
sample = "geeks"

# function call
find(string, sample)

sample = "makes"

# function call
find(string, sample)
```

**输出:**

```py
string starts with the given substring
string doesn't start with the given substring
```

**方法 2:**
这里，我们首先检查字符串中是否存在给定的子字符串，如果是，那么我们使用 **re library 的 **search()** 函数以及元字符**“\ A”。**这个元字符检查给定的字符串是否从提供的子字符串开始。**

下面是上述方法的实现:

## 蟒蛇 3

```py
# import library
import re

# define a function 
def find(string, sample) :

  # check substring present 
  # in a string or not
  if (sample in string):

      y = "\A" + sample

      # check if string starts 
      # with the substring
      x = re.search(y, string)

      if x :
          print("string starts with the given substring")

      else :
          print("string doesn't start with the given substring")

  else :
      print("entered string isn't a substring")

# Driver code
string = "geeks for geeks makes learning fun"  
sample = "geeks"

# function call
find(string, sample)

sample = "makes"

# function call
find(string, sample)
```

**输出:**

```py
string starts with the given substring
string doesn't start with the given substring
```