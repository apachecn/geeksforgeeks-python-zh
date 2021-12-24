# Python–将浮点字符串列表转换为浮点值

> 原文:[https://www . geesforgeks . org/python-convert-float-string-list-to-float-values/](https://www.geeksforgeeks.org/python-convert-float-string-list-to-float-values/)

有时，在使用 Python 数据时，我们可能会遇到一个问题，即我们需要执行浮点字符串到浮点值的转换。这种问题在所有领域都很常见，并且经常得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = ['8.6 '，' 4.6']
> **输出** : [8.6，4.6]
> 
> **输入** : test_list = ['4.5']
> **输出** : [4.5]

**方法#1:使用列表理解+ `float()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 float()执行转换任务，并使用列表理解来执行迭代。

```py
# Python3 code to demonstrate working of 
# Convert Float String List to Float Values
# Using float() + list comprehension

# initializing list
test_list = ['87.6', '454.6', '9.34', '23', '12.3']

# printing original list 
print("The original list : " + str(test_list))

# Convert Float String List to Float Values
# Using float() + list comprehension
res = [float(ele) for ele in test_list]

# printing result 
print("List after conversion : " + str(res))
```

**Output :**

```py
The original list : ['87.6', '454.6', '9.34', '23', '12.3']
List after conversion : [87.6, 454.6, 9.34, 23.0, 12.3]

```

**方法 2:使用`map() + float()`**
以上功能的组合也可以用来解决这个问题。在本文中，我们使用 float 执行转换任务，并使用 map()扩展转换逻辑。

```py
# Python3 code to demonstrate working of 
# Convert Float String List to Float Values
# Using map() + float()

# initializing list
test_list = ['87.6', '454.6', '9.34', '23', '12.3']

# printing original list 
print("The original list : " + str(test_list))

# Convert Float String List to Float Values
# Using map() + float()
res = list(map(float, test_list))

# printing result 
print("List after conversion : " + str(res))
```

**Output :**

```py
The original list : ['87.6', '454.6', '9.34', '23', '12.3']
List after conversion : [87.6, 454.6, 9.34, 23.0, 12.3]

```