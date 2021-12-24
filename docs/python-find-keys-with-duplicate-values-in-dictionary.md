# Python |在字典中查找重复值的键

> 原文:[https://www . geesforgeks . org/python-查找字典中有重复值的键/](https://www.geeksforgeeks.org/python-find-keys-with-duplicate-values-in-dictionary/)

给定一个字典，任务是找到具有重复值的键。让我们讨论几个相同的方法。

**方法#1:使用朴素方法**
在该方法中，我们首先使用逆映射将字典值转换为关键字，然后找到重复的关键字

```py
# Python code to demonstrate 
# finding duplicate values from a dictionary

# initialising dictionary
ini_dict = {'a':1, 'b':2, 'c':3, 'd':2}

# printing initial_dictionary
print("initial_dictionary", str(ini_dict))

# finding duplicate values
# from dictionary
# using a naive approach
rev_dict = {}

for key, value in ini_dict.items():
    rev_dict.setdefault(value, set()).add(key)

result = [key for key, values in rev_dict.items()
                              if len(values) > 1]

# printing result
print("duplicate values", str(result))
```

**Output:**

```py
initial_dictionary {'c': 3, 'b': 2, 'd': 2, 'a': 1}
duplicate values [2]

```