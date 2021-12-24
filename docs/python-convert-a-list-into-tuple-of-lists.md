# Python |将列表转换为列表元组

> 原文:[https://www . geesforgeks . org/python-将列表转换为列表元组/](https://www.geeksforgeeks.org/python-convert-a-list-into-tuple-of-lists/)

给我们一个列表，任务是将列表转换成列表的元组。

```
Input: ['Geeks', 'For', 'geeks']
Output: (['Geeks'], ['For'], ['geeks'])

Input: ['first', 'second', 'third']
Output: (['first'], ['second'], ['third'])

```

**方法#1 :** 使用理解

```
# Python code to convert a list into tuple of lists

# Initialisation of list
Input = ['Geeks', 'for', 'geeks']

# Using list Comprehension
Output = tuple([name] for name in Input)

# printing output
print(Output)
```

**Output:**

```
(['Geeks'], ['for'], ['geeks'])

```