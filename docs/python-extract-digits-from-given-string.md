# Python |从给定字符串中提取数字

> 原文:[https://www . geesforgeks . org/python-从给定字符串中提取数字/](https://www.geeksforgeeks.org/python-extract-digits-from-given-string/)

在编程时，有时，我们只需要某种类型的数据，而需要丢弃其他数据。这种类型的问题在数据科学领域非常常见，由于数据科学在全球范围内使用 Python，因此了解如何提取特定元素非常重要。本文讨论了某些只能提取数字的方法。我们也来讨论一下。

**方法#1:使用`join() + isdigit() + filter()`**

可以使用上述功能的组合来执行该任务。过滤功能过滤由 isdigit 功能检测到的数字，连接功能执行连接功能的重构任务。

```py
# Python3 code to demonstrate
# Extract digit string 
# using join() + isdigit() + filter()

# initializing string
test_string = 'g1eeks4geeks5'

# printing original strings  
print("The original string : " + test_string)

# using join() + isdigit() + filter()
# Extract digit string 
res = ''.join(filter(lambda i: i.isdigit(), test_string))

# print result
print("The digits string is : " + str(res))
```

**Output :**

```py
The original string : g1eeks4geeks5
The digits string is : 145

```

**方法 2:使用`re`**
正则表达式也可以用来执行这个特定的任务。我们可以使用“\D”定义数字类型要求，并且只从字符串中提取数字。

```py
# Python3 code to demonstrate
# Extract digit string 
# using re
import re

# initializing string
test_string = 'g1eeks4geeks5'

# printing original strings  
print("The original string : " + test_string)

# using re
# Extract digit string 
res = re.sub("\D", "", test_string)

# print result
print("The digits string is : " + str(res))
```

**Output :**

```py
The original string : g1eeks4geeks5
The digits string is : 145

```