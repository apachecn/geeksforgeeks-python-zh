# Python |将字符串范围转换为列表

> 原文:[https://www . geesforgeks . org/python-convert-string-ranges-to-list/](https://www.geeksforgeeks.org/python-convert-string-ranges-to-list/)

有时，在应用程序中工作时，我们可能会遇到这样一个问题:给我们一个简单的字符串，该字符串提供由连字符分隔的范围和由逗号分隔的其他数字。这个问题可能会在许多地方出现。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`sum() + split()` +列表理解+ `enumerate()`**
以上功能的组合可以用来执行这些任务。在这种情况下，对连字符和逗号以及相应的范围执行拆分，数字被提取并编译成列表。

```py
# Python3 code to demonstrate working of
# Convert String ranges to list
# Using sum() + list comprehension + enumerate() + split()

# initializing string 
test_str = "1, 4-6, 8-10, 11"

# printing original string 
print("The original string is : " + test_str)

# Convert String ranges to list
# Using sum() + list comprehension + enumerate() + split()
res = sum(((list(range(*[int(b) + c 
           for c, b in enumerate(a.split('-'))]))
           if '-' in a else [int(a)]) for a in test_str.split(', ')), [])

# printing result
print("List after conversion from string : " + str(res))
```

**Output :**

```py
The original string is : 1, 4-6, 8-10, 11
List after conversion from string : [1, 4, 5, 6, 8, 9, 10, 11]

```