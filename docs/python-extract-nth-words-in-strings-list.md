# Python |提取字符串列表中的第 n 个单词

> 原文:[https://www . geeksforgeeks . org/python-extract-n-in-words-list/](https://www.geeksforgeeks.org/python-extract-nth-words-in-strings-list/)

有时，在使用 Python Lists 时，我们可能会遇到这样的问题:我们需要执行提取 List 中每个字符串的第 n 个单词的任务。这可以在网络开发领域得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `split()`**
以上方法的组合可以用来解决这个问题。在本文中，我们执行了使用拆分获得第 n 个单词和使用列表理解重新创建列表的任务。

```py
# Python3 code to demonstrate working of 
# Extract Nth words in Strings List
# Using list comprehension + split()

# initializing list
test_list = ['Gfg best for', 'All geeks', 'It is for', 'all CS professionals']

# printing original list
print("The original list is : " + str(test_list))

# initializing N 
N = 2

# Extract Nth words in Strings List
# Using list comprehension + split()
res = [sub.split()[N - 1] for sub in test_list if len(sub.split()) > 1]

# printing result 
print("The Nth words in list are : " + str(res)) 
```

**Output :**

```py
The original list is : ['Gfg best for', 'All geeks', 'It is for', 'all CS professionals']
The Nth words in list are : ['best', 'geeks', 'is', 'CS']

```