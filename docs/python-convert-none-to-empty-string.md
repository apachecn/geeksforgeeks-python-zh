# Python |无转换为空字符串

> 原文:[https://www . geesforgeks . org/python-convert-none-to-empty-string/](https://www.geeksforgeeks.org/python-convert-none-to-empty-string/)

有时，在使用机器学习时，我们会遇到无值，为了数据一致性，我们希望转换为空字符串。这个和许多其他实用程序可能需要解决这个问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用λ**
这个任务可以使用λ函数来执行。在本例中，我们使用 or 运算符检查无字符串或空字符串，并用空字符串替换无值。

```py
# Python3 code to demonstrate working of
# Converting None to empty string
# Using lambda

# initializing list of strings
test_list = ["Geeks", None, "CS", None, None]

# printing original list 
print("The original list is : " + str(test_list))

# using lambda
# Converting None to empty string
conv = lambda i : i or ''
res = [conv(i) for i in test_list]

# printing result 
print("The list after conversion of None values : " + str(res))
```

**Output :**

```py
The original list is : ['Geeks', None, 'CS', None, None]
The list after conversion of None values : ['Geeks', '', 'CS', '', '']

```