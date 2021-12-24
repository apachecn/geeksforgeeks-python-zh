# Python–使用无值列表创建字典

> 原文:[https://www . geesforgeks . org/python-create-a-dictionary-using-list-with-none-values/](https://www.geeksforgeeks.org/python-create-a-dictionary-using-list-with-none-values/)

有时，您可能需要将列表转换为 dict 对象，以便进行更好更快的操作。让我们看看如何将列表转换为无值字典。在这里我们会找到三种方法。

**方法#1:** 使用 zip()和 dict

## python 3

```py
# Python code to demonstrate
# converting list into dictionary with none values
# using zip() and dictionary

# initializing list
ini_list = [1, 2, 3, 4, 5]

# printing initialized list
print ("initial list", str(ini_list))

# Converting list into dictionary using zip() and dictionary
res = dict(zip(ini_list, [None]*len(ini_list)))

# printing final result
print ("final dictionary", str(res))
```

**输出:**

```py
initial list [1, 2, 3, 4, 5]
final dictionary {1: None, 2: None, 3: None, 4: None, 5: None}
```