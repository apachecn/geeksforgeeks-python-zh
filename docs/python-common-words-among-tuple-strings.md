# Python |元组串中的常用词

> 原文:[https://www . geesforgeks . org/python-元组字符串中的常用词/](https://www.geeksforgeeks.org/python-common-words-among-tuple-strings/)

有时，在处理元组时，我们会遇到一个问题，即我们需要找到以字符串为元素的单元组内字符串中出现的单词的交集。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`join() + set() + & operator + split()`**
上述功能的组合可用于执行该特定任务。在这种情况下，我们首先将每个元组转换为集合，然后执行由`split()`分割的元素单词的交集。最后一步是使用`join()`连接所有公共元素。

```
# Python3 code to demonstrate working of
# Common words among tuple strings
# Using join() + set() + & operator + split()

# Initializing tuple 
test_tup = ('gfg is best', 'gfg is for geeks', 'gfg is for all')

# printing original tuple 
print("The original tuple is : " + str(test_tup))

# Common words among tuple strings
# Using join() + set() + & operator + split()
res = ", ".join(sorted(set(test_tup[0].split()) &\
          set(test_tup[1].split()) &\
          set(test_tup[2].split())))

# printing result
print("Common words among tuple are : " + res)
```

**Output :**

```
The original tuple is : ('gfg is best', 'gfg is for geeks', 'gfg is for all')
Common words among tuple are : gfg, is

```