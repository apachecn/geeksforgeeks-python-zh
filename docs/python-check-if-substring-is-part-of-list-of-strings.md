# Python |检查子字符串是否是字符串列表的一部分

> 原文:[https://www . geesforgeks . org/python-检查子字符串是否是字符串列表的一部分/](https://www.geeksforgeeks.org/python-check-if-substring-is-part-of-list-of-strings/)

子串的许多问题已经被处理了很多次。还可能存在这样的问题，即我们需要检查参数字符串是否是输入字符串列表中任何字符串的一部分。让我们讨论一下实现这一点的各种方法。

**方法#1:使用`join()`**
可用于执行该特定任务的基本方法是计算所有列表字符串的连接，然后在连接的字符串中搜索该字符串。

```
# Python3 code to demonstrate working of
# Check if substring is part of List of Strings
# Using join()

# initializing list  
test_list = ['GeeksforGeeks', 'is', 'Best']

# test string 
check_str = "for"

# printing original string 
print("The original string is : " + str(test_list))

# Using join()
# Check if substring is part of List of Strings
temp = '\t'.join(test_list)
res = check_str in temp

# printing result 
print("Is check string part of any input list string : " + str(res))
```

**Output :**

```
The original string is : ['GeeksforGeeks', 'is', 'Best']
Is check string part of any input list string : True

```