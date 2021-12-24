# Python–字典值划分

> 原文:[https://www . geesforgeks . org/python-dictionary-values-division/](https://www.geeksforgeeks.org/python-dictionary-values-division/)

有时，在使用字典时，我们可能会遇到效用问题，需要在字典的公共键之间执行基本操作。这可以扩展到要执行的任何操作。让我们在本文中讨论相似关键值的划分和解决方法。

**方法#1:使用字典理解+ `keys()`**
以上两者的结合可以用来执行这个特定的任务。这只是较长循环方法的简写，可以用来在一行中执行此任务。

```
# Python3 code to demonstrate working of
# Dictionary Values Division
# Using dictionary comprehension + keys()

# Initialize dictionaries
test_dict1 = {'gfg' : 20, 'is' : 24, 'best' : 100}
test_dict2 = {'gfg' : 10, 'is' : 6, 'best' : 10}

# printing original dictionaries 
print("The original dictionary 1 : " + str(test_dict1))
print("The original dictionary 2 : " + str(test_dict2))

# Using dictionary comprehension + keys()
# Dictionary Values Division
res = {key: test_dict1[key] // test_dict2.get(key, 0)
                        for key in test_dict1.keys()}

# printing result 
print("The divided dictionary is : " + str(res))
```

**Output :**

```
The original dictionary 1 : {'is': 24, 'best': 100, 'gfg': 20}
The original dictionary 2 : {'is': 6, 'best': 10, 'gfg': 10}
The divided dictionary is : {'is': 4, 'best': 10, 'gfg': 2}

```