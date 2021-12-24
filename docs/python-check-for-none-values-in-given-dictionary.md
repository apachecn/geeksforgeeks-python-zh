# Python |检查给定字典中的无值

> 原文:[https://www . geesforgeks . org/python-检查给定字典中的无值/](https://www.geeksforgeeks.org/python-check-for-none-values-in-given-dictionary/)

很多时候，在使用字典时，我们希望检查非空字典，即检查给定字典中的无值。这在机器学习中得到了应用，在机器学习中，我们必须输入没有任何值的数据。让我们讨论执行这项任务的某些方法。

**方法#1:使用`all() + not operator + values()`**

上述功能的组合可用于执行该特定任务。在本例中，我们使用`values`函数提取的`all`函数检查所有值。 `not`运算符用于对结果求逆，以检查是否有任何“无”值。

```py
# Python3 code to demonstrate working of
# Check for Non None Dictionary values
# Using all() + not operator + values()

# initializing dictionary
test_dict = {'Gfg' : 1, 'for' : 2, 'CS' : None}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using all() + not operator + values()
# Check for Non None Dictionary values
res = not all(test_dict.values())

# printing result 
print("Does Dictionary contain None value ? " + str(res))
```

**Output :**

```py
The original dictionary is : {'Gfg': 1, 'CS': None, 'for': 2}
Does Dictionary contain None value ? True

```

**方法 2:使用`in operator + values()`**

也可以使用 in 运算符和值函数来执行此任务。我们只需在使用`values`函数提取的所有值中检查无，并使用`in`运算符检查是否存在。

```py
# Python3 code to demonstrate working of
# Check for Non None Dictionary values
# Using in operator + values()

# initializing dictionary
test_dict = {'Gfg' : 1, 'for' : 2, 'CS' : None}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using in operator + values()
# Check for Non None Dictionary values
res = None in test_dict.values()

# printing result 
print("Does Dictionary contain None value ? " + str(res))
```

**Output :**

```py
The original dictionary is : {'Gfg': 1, 'CS': None, 'for': 2}
Does Dictionary contain None value ? True

```