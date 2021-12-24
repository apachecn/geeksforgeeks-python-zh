# Python |将元组记录转换为单个字符串

> 原文:[https://www . geesforgeks . org/python-convert-tuple-records-to-single-string/](https://www.geeksforgeeks.org/python-convert-tuple-records-to-single-string/)

有时，在处理数据时，我们可能会遇到元组记录的问题，我们需要将其更改为逗号分隔的字符串。这些可以是关于名字的数据。这类问题在 web 开发领域有其应用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`join()` +列表理解**
在该方法中，我们只需遍历列表元组元素，并在它们之间执行由空格分隔的连接，以将它们连接为单个记录字符串。

```py
# Python3 code to demonstrate working of
# Convert tuple records to single string
# Using list comprehension + join()

# Initializing list
test_list = [('Manjeet', 'Singh'), ('Nikhil', 'Meherwal'), ('Akshat', 'Garg')]

# printing original list
print("The original list is : " + str(test_list))

# Convert tuple records to a single string
# Using list comprehension + join()
res = ', '.join([' '.join(sub) for sub in test_list])

# printing result
print("The string after tuple conversion: " + res)
```

**Output :**

```py
The original list is : [('Manjeet', 'Singh'), ('Nikhil', 'Meherwal'), ('Akshat', 'Garg')]
The string after tuple conversion: Manjeet Singh, Nikhil Meherwal, Akshat Garg

```