# Python |从给定字典中过滤负值

> 原文:[https://www . geesforgeks . org/python-过滤给定字典中的负值/](https://www.geeksforgeeks.org/python-filter-the-negative-values-from-given-dictionary/)

给定一个字典，任务是过滤给定字典中的所有负值。让我们讨论一些方法来完成这项任务。

**方法#1:使用字典理解**

```
# Python code to demonstrate
# return the filtered dictionary
# on certain criteria

from six import iteritems
# Initialising dictionary
ini_dict = {'a':1, 'b':-2, 'c':-3, 'd':7, 'e':0}

# printing initial dictionary
print ("initial lists", str(ini_dict))

# filter dictionary such that no value is greater than 0
result = dict((k, v) for k, v in ini_dict.items() if v >= 0)

print("resultant dictionary : ", str(result))
```

**Output:**

```
initial lists {'a': 1, 'c': -3, 'd': 7, 'b': -2, 'e': 0}
resultant dictionary :  {'a': 1, 'd': 7, 'e': 0}

```

**方法 2:使用λ和滤波器**

```
# Python code to demonstrate
# return the filtered dictionary
# on certain criteria

from six import iteritems
# Initialising dictionary
ini_dict = {'a':1, 'b':-2, 'c':-3, 'd':7, 'e':0}

# printing initial dictionary
print ("initial lists", str(ini_dict))

# filter dictionary such that no value is greater than 0
result = dict(filter(lambda x: x[1] >= 0.0, ini_dict.items()))
result = dict(result)

print("resultant dictionary : ", str(result))
```

**Output:**

```
initial lists {'c': -3, 'd': 7, 'e': 0, 'a': 1, 'b': -2}
resultant dictionary :  {'e': 0, 'a': 1, 'd': 7}

```