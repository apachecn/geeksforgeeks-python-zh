# Python |统计字符串中某个字符的出现次数

> 原文:[https://www . geesforgeks . org/python-字符串中字符的出现次数/](https://www.geeksforgeeks.org/python-count-occurrences-of-a-character-in-string/)

给定一个字符串，任务是计算该字符串中单个字符的频率。这种对字符串的特殊操作在许多应用程序中非常有用，例如删除重复或检测不需要的字符。

**方法#1 :** 幼稚方法

迭代该特定字符的整个字符串，然后在遇到该特定字符时增加计数器。

```
# Python3 code to demonstrate 
# occurrence frequency using 
# naive method 

# initializing string 
test_str = "GeeksforGeeks"

# using naive method to get count 
# counting e 
count = 0

for i in test_str:
    if i == 'e':
        count = count + 1

# printing result 
print ("Count of e in GeeksforGeeks is : "
                            +  str(count))
```

**输出:**

```
Count of e in GeeksforGeeks is : 4
```

**方法 2 :** 使用`count()`

使用`count()`是 Python 中获取任意容器中任意元素的出现最常规的方法。这很容易编码和记忆，因此很受欢迎。

```
# Python3 code to demonstrate 
# occurrence frequency using 
# count()

# initializing string 
test_str = "GeeksforGeeks"

# using count() to get count 
# counting e 
counter = test_str.count('e')

# printing result 
print ("Count of e in GeeksforGeeks is : "
                           +  str(counter))
```

**输出:**

```
Count of e in GeeksforGeeks is : 4

```

**方法 3 :** 使用`collections.Counter()`

这是在 Python 中跨任何容器获取元素出现的一种不太为人所知的方法。这也执行类似于上面两个方法的任务，只是一个不同的库即集合的功能。

```
# Python3 code to demonstrate 
# occurrence frequency using 
# collections.Counter()
from collections import Counter

# initializing string 
test_str = "GeeksforGeeks"

# using collections.Counter() to get count 
# counting e 
count = Counter(test_str)

# printing result 
print ("Count of e in GeeksforGeeks is : "
                       +  str(count['e']))
```

**输出:**

```
Count of e in GeeksforGeeks is : 4

```

**方法 4 :** 使用λ+`sum()`+`map()`

Lambda 函数与`sum()`和 `map()`一起可以实现统计字符串中特定元素的总出现次数的特定任务。这使用 `sum()`来总结使用 `map()`获得的所有事件。

```
# Python3 code to demonstrate 
# occurrence frequency using 
# lambda + sum() + map()

# initializing string 
test_str = "GeeksforGeeks"

# using lambda + sum() + map() to get count 
# counting e 
count = sum(map(lambda x : 1 if 'e' in x else 0, test_str))

# printing result 
print ("Count of e in GeeksforGeeks is : "
                            +  str(count))
```

**输出:**

```
Count of e in GeeksforGeeks is : 4

```

**方法 5 :** 使用`re + findall()`

正则表达式可以帮助我们完成许多与字符串相关的编码任务。它们还可以帮助我们完成查找字符串中元素出现的任务。

```
# Python3 code to demonstrate 
# occurrence frequency using 
# re + findall()
import re

# initializing string 
test_str = "GeeksforGeeks"

# using re + findall() to get count 
# counting e 
count = len(re.findall("e", test_str))

# printing result 
print ("Count of e in GeeksforGeeks is : "
                            +  str(count))
```

**输出:**

```
Count of e in GeeksforGeeks is : 4

```