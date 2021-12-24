# Python |列表值字典中的元素出现次数

> 原文:[https://www . geesforgeks . org/python-元素-值列表字典中出现/](https://www.geeksforgeeks.org/python-element-occurrence-in-dictionary-of-list-values/)

有时我们会有一个任务，要求我们计算列表中测试元素的出现次数或获胜次数，与列表中具有相关键的数值进行比较。这可以在游戏或其他实用程序中应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用字典理解+ `sum()`**
这个任务可以使用上面两个实用程序的组合来执行，其中我们使用字典理解来绑定逻辑，求和函数可以用来对从测试列表中找到的匹配进行求和。

```py
# Python3 code to demonstrate
# Element Occurrence in dictionary value list
# using list comprehension + sum()

# initializing dictionary
test_dict = { "Akshat" : [1, 4, 5, 3],
              "Nikhil" : [4, 6],
              "Akash" : [5, 2, 1] }

# initializing test list 
test_list = [2, 1]

# printing original dict
print("The original dictionary : " + str(test_dict))

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + sum()
# Element Occurrence in dictionary value list
res = {idx : sum(1 for i in j if i in test_list)
                for idx, j in test_dict.items()}

# print result
print("The summation of element occurrence : " + str(res))
```

**Output :**

```py
The original dictionary : {'Nikhil': [4, 6], 'Akshat': [1, 4, 5, 3], 'Akash': [5, 2, 1]}
The original list : [2, 1]
The summation of element occurrence : {'Nikhil': 0, 'Akshat': 1, 'Akash': 2}

```