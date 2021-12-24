# Python–检查字符串是否以列表

中的任何元素开头

> 原文:[https://www . geesforgeks . org/python-check-if-string-以列表中的任何元素开头/](https://www.geeksforgeeks.org/python-check-if-string-starts-with-any-element-in-list/)

在处理字符串时，它们的前缀和后缀在任何决策中都起着重要的作用。对于数据操作任务，我们有时可能需要检查一个字符串是否以任何匹配的字符串开头。让我们讨论执行这项任务的某些方法。

**方法#1:使用`filter() + startswith()`**
以上功能的组合可以帮助执行这个特定的任务。filter 方法用于检查每个单词，并从目标列表中前缀逻辑的方法测试开始。

```
# Python3 code to demonstrate
# Prefix tests in Strings
# using filter() + startswith()

# initializing string 
test_string = "GfG is best"

# initializing prefix list
pref_list = ['best', 'GfG', 'good']

# printing original string 
print("The original string : " + str(test_string))

# using filter() + startswith()
# Prefix tests in Strings
res = list(filter(test_string.startswith, pref_list)) != []

# print result
print("Does string start with any prefix list sublist ? : " + str(res))
```

**Output :**

```
The original string : GfG is best
Does string start with any prefix list sublist ? : True

```