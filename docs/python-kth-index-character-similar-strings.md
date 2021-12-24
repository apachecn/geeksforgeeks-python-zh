# Python | Kth 索引字符相似字符串

> 原文:[https://www . geesforgeks . org/python-kth-index-character-similar-strings/](https://www.geeksforgeeks.org/python-kth-index-character-similar-strings/)

有时，我们要求得到带有特定字母的 Kth 索引的单词。这种用例在普通编程项目或竞争性编程中非常常见。让我们讨论用 Python 处理这个问题的某些速记。

**方法#1:使用列表理解+ `lower()`**
这个问题可以通过使用上述两个函数的组合来解决，列表理解执行将逻辑扩展到整个列表的任务，并且较低的函数检查与参数字母的目标单词的大小写不敏感性。

```
# Python3 code to demonstrate
# Kth index character similar Strings
# using list comprehension + lower()

# initializing list
test_list = ['Akash', 'Nikhil', 'Manjeet', 'akshat']

# initializing check letter
check = 'k'

# initializing K 
K = 2

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + lower()
# Kth index character similar Strings
res = [idx for idx in test_list if idx[K - 1].lower() == check.lower()]

# print result
print("The list of matching Kth letter : " + str(res))
```

**Output :**

```
The original list : ['Akash', 'Nikhil', 'Manjeet', 'akshat']
The list of matching Kth letter : ['Akash', 'akshat']

```