# Python–提取数字字典值

> 原文:[https://www . geesforgeks . org/python-extract-numeric-dictionary-values/](https://www.geeksforgeeks.org/python-extract-numerical-dictionary-values/)

有时，在使用 Python Dictionaries 时，我们会遇到这样一个问题，即只有当特定的键索引是字符串形式的字典中的数值时，我们才需要提取。这在我们需要进行预处理的应用中是需要的。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'best': ['5 '，' 35 '，' geeks']，' CS': [1，2，3]，' Gfg': ['124 '，' 4 '，' 8']}
> **输出** : [('5 '，1，' 124 ')，(' 35 '，2，' 4')]
> 
> **输入**:test _ dict = {“Gfg”:[“4”]，“best”:[“6”]，“CS”:[1]}
> **输出**:[(‘6’，1，‘4’)]

**方法#1:使用 loop + `zip() + isdigit()`**
以上功能的组合可以用来执行这个任务。在本文中，我们使用 isdigit()和 zip 来检查数字字符串，以执行键的累积。

```py
# Python3 code to demonstrate working of 
# Extract Numerical Dictionary values
# Using loop + zip() + isdigit()

# initializing dictionary
test_dict = {"Gfg" : ["34", "45", 'geeks'], 'is' : ["875", None, "15"], 'best' : ["98", 'abc', '12k']}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Extract Numerical Dictionary values
# Using loop + zip() + isdigit()
res = []
for a, b, c in zip(*test_dict.values()):
    if a.isdigit() :
        res.append((a, b, c))

# printing result 
print("The Numerical values : " + str(res)) 
```

**Output :**

> 原始字典:{'Gfg': ['34 '，' 45 '，'极客']，' best': ['98 '，' abc '，' 12k']，' is': ['875 '，' None，' 15']}
> 数值:[('34 '，' 98 '，' 875 ')，(' 45 '，' abc '，None)]

**方法 2:使用列表理解+ `zip() + isdigit()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们执行与上述方法类似的任务，但使用列表理解作为速记。

```py
# Python3 code to demonstrate working of 
# Extract Numerical Dictionary values
# Using list comprehension + zip() + isdigit()

# initializing dictionary
test_dict = {"Gfg" : ["34", "45", 'geeks'], 'is' : ["875", None, "15"], 'best' : ["98", 'abc', '12k']}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Extract Numerical Dictionary values
# Using list comprehension + zip() + isdigit()
res = [(a, b, c) for a, b, c in zip(*test_dict.values()) if a.isdigit()]

# printing result 
print("The Numerical values : " + str(res)) 
```

**Output :**

> 原始字典:{'Gfg': ['34 '，' 45 '，'极客']，' best': ['98 '，' abc '，' 12k']，' is': ['875 '，' None，' 15']}
> 数值:[('34 '，' 98 '，' 875 ')，(' 45 '，' abc '，None)]