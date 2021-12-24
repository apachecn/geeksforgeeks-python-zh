# Python |在列表中查找字典匹配值

> 原文:[https://www . geesforgeks . org/python-find-dictionary-matching-value-in-list/](https://www.geeksforgeeks.org/python-find-dictionary-matching-value-in-list/)

当一个人开始使用字典时，只获得具有对应键的特定值的合适字典的问题是很常见的。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。为此，我们只需使用简单的检查和比较，一旦找到合适的匹配，就返回结果，并为其他字典中断。

```py
# Python3 code to demonstrate working of
# Find dictionary matching value in list
# Using loop

# Initialize list
test_list = [{'gfg' : 2, 'is' : 4, 'best' : 6}, 
             {'it' : 5, 'is' : 7, 'best' : 8},
             {'CS' : 10}]

# Printing original list
print("The original list is : " + str(test_list))

# Using loop
# Find dictionary matching value in list
res = None
for sub in test_list:
    if sub['is'] == 7:
        res = sub
        break

# printing result 
print("The filtered dictionary value is : " + str(res))
```

**Output :**

```py
The original list is : [{'is': 4, 'gfg': 2, 'best': 6}, {'is': 7, 'best': 8, 'it': 5}, {'CS': 10}]
The filtered dictionary value is : {'is': 7, 'best': 8, 'it': 5}

```