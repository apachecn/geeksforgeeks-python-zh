# Python |从列表中移除重复子串

> 原文:[https://www . geesforgeks . org/python-重复-子串-从列表中删除/](https://www.geeksforgeeks.org/python-duplicate-substring-removal-from-list/)

有时我们会遇到这样的问题，我们需要处理列表中的某些字符串，这些字符串由一些分隔符分隔，我们需要删除每种字符串中的重复项。简单的人手不足来解决这种问题总是好的。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`set() + split()`**
这个特殊的问题可以通过使用 split 函数来解决，该函数具有目标字符串，然后进行设置，实际上可以消除字符串的重复。

```
# Python3 code to demonstrate
# removing duplicate substrings
# using set() + split()

# initializing list
test_list = [ 'aa-aa-bb', 'bb-cc', 'gg-ff-gg', 'hh-hh']

# printing original list
print("The original list : " + str(test_list))

# using set() + split()
# removing duplicate substrings
res = [set(sub.split('-')) for sub in test_list]

# print result
print("The list after duplicate removal : " + str(res))
```

**Output :**

```
The original list : ['aa-aa-bb', 'bb-cc', 'gg-ff-gg', 'hh-hh']
The list after duplicate removal : [{'aa', 'bb'}, {'cc', 'bb'}, {'gg', 'ff'}, {'hh'}]

```