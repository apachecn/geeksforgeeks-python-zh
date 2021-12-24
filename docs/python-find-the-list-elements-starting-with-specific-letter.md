# Python |找到以特定字母

开头的列表元素

> 原文:[https://www . geesforgeks . org/python-find-the-list-elements-以特定字母开头/](https://www.geeksforgeeks.org/python-find-the-list-elements-starting-with-specific-letter/)

有时，我们要求得到以特定字母开头的单词。这种用例在普通编程项目或竞争性编程中非常常见。让我们讨论一下 Python 中处理这个问题的一些技巧。

**方法一:使用列表理解+ `lower()`**

这个问题可以通过使用上述两个函数的组合来解决，列表理解执行将逻辑扩展到整个列表的任务，并且较低的函数检查与参数字母的目标单词的大小写不敏感性。

```
# Python3 code to demonstrate
# Words starting with specific letter
# using list comprehension + lower()

# initializing list
test_list = ['Akash', 'Nikhil', 'Manjeet', 'akshat']

# initializing check letter
check = 'A'

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + lower()
# Words starting with specific letter
res = [idx for idx in test_list if idx[0].lower() == check.lower()]

# print result
print("The list of matching first letter : " + str(res))
```

**Output :**

```
The original list : ['Akash', 'Nikhil', 'Manjeet', 'akshat']
The list of matching first letter : ['Akash', 'akshat']

```

**方法 2:使用列表理解+ `startswith() + lower()`**

这个方法类似于上面的方法，但是它不是使用运算符检查是否相等，而是使用由 python 内置库提供的 startswith 函数进行检查。

```
# Python3 code to demonstrate
# Words starting with specific letter
# using list comprehension + startswith() + lower()

# initializing list
test_list = ['Akash', 'Nikhil', 'Manjeet', 'akshat']

# initializing check letter
check = 'A'

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + startswith() + lower()
# Words starting with specific letter
res = [idx for idx in test_list if idx.lower().startswith(check.lower())]

# print result
print("The list of matching first letter : " + str(res))
```

**Output :**

```
The original list : ['Akash', 'Nikhil', 'Manjeet', 'akshat']
The list of matching first letter : ['Akash', 'akshat']

```