# Python |第一个出现在后字符串中的字符

> 原文:[https://www . geesforgeks . org/python-第一个字符-出现-从后开始-字符串/](https://www.geeksforgeeks.org/python-first-character-occurrence-from-rear-string/)

有许多方法可以找到字符串中元素的第一个索引，因为 python 在其语言中提供了 index()函数，该函数返回字符串中元素第一次出现的索引。但是，如果希望得到字符串中元素的最后一次出现，通常需要应用一个更长的方法。让我们讨论一下某些人手不足的人如何完成这项特殊任务。

**方法#1:使用`rfind()`**
这通常是我们可以用来完成这个任务的黑客。使用字符串函数 rfind()从右侧获取第一个元素，即字符串中元素的最后一个索引。

```
# Python 3 code to demonstrate 
# First character occurrence from rear String
# using rfind()

# initializing string
test_str = "Geeksforgeeks"

# printing original string
print ("The original string is : " + str(test_str))

# using rfind()
# to get last element occurrence
res = test_str.rfind('e')

# printing result
print ("The index of last element occurrence: " + str(res))
```

**Output :**

```
The original string is : Geeksforgeeks
The index of last element occurrence: 10

```