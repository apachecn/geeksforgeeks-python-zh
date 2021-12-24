# Python |检查字符串中是否存在子字符串

> 原文:[https://www . geesforgeks . org/python-check-if-substring-in-string/](https://www.geeksforgeeks.org/python-check-if-substring-present-in-string/)

让我们来解决这个一般性的问题，即寻找一个特定的字符串是否以不同的方式出现在一个更大的字符串中。这是每个程序员一生中最常遇到的一种问题。本文给出了解决这个问题的各种技术。

**方法 1:使用`in`运算符**
`in`运算符是检查一个子串最通用、最快的方法，python 中`in`运算符的威力是众所周知的，它被用于整个语言的许多操作中。

```py
# Python 3 code to demonstrate 
# checking substring in string
# using in operator

# initializing string 
test_str = "GeeksforGeeks"

# using in to test
# for substring
print ("Does for exists in GeeksforGeeks ? : ")
if "for" in test_str :
    print ("Yes, String found")
else : 
    print ("No, String not found")
```

**输出:**

```py
Does for exists in GeeksforGeeks ? : 
Yes, String found

```

**方法 2:使用`str.find()`**
**str.find()** 方法一般用于获取字符串出现的最低索引，但如果字符串不存在，也返回-1，因此如果有任何值返回> = 0，则字符串存在，否则不存在。

```py
# Python 3 code to demonstrate 
# checking substring in string
# using str.find()

# initializing string 
test_str = "GeeksforGeeks"

# using str.find() to test
# for substring
res = test_str.find("for")
if res >= 0:
    print ("for is present in GeeksforGeeks")
else :
    print ("for is not present in GeeksforGeeks")
```

**输出:**

```py
for is present in GeeksforGeeks

```

**方法 3:使用`str.index()`**
这个方法可以用来执行类似的任务，但是和 str.find()一样，它不返回值，但是如果字符串不存在，它会返回一个 ValueError，因此捕捉异常是检查子字符串中字符串的方法。

```py
# Python 3 code to demonstrate 
# checking substring in string
# using str.index()

# initializing string 
test_str = "GeeksforGeeks"

# using str.index() to test
# for substring
try : 
    res = test_str.index("forg")
    print ("forg exists in GeeksforGeeks")
except :
    print ("forg does not exists in GeeksforGeeks")
```

**输出:**

```py
forg does not exists in GeeksforGeeks

```

**方法 4:使用`operator.contains()`**
这是一种不太为人所知的检查字符串中的子字符串的方法，这种方法在完成检查字符串中的字符串的任务时也是有效的。

```py
# Python 3 code to demonstrate 
# checking substring in string
# using operator.contains()
import operator

# initializing string 
test_str = "GeeksforGeeks"

# using operator.contains() to test
# for substring
if operator.contains(test_str, "for"):
    print ("for is present in GeeksforGeeks")
else :
    print ("for is not present in GeeksforGeeks")
```

**输出:**

```py
for is present in GeeksforGeeks

```