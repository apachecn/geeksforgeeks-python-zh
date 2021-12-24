# Python |通过键相交两个字典

> 原文:[https://www . geesforgeks . org/python-intersect-two-dictionary-through-keys/](https://www.geeksforgeeks.org/python-intersect-two-dictionaries-through-keys/)

给定两个字典，任务是通过键找到这两个字典的交集。让我们看看完成这项任务的不同方法。

**方法一:使用字典理解**

```py
# Python code to demonstrate
# intersection of two dictionaries 
# using dict comprehension

# inititialising dictionary
ini_dict1 = {'nikhil': 1, 'vashu' : 5, 
             'manjeet' : 10, 'akshat' : 15}
ini_dict2 = {'akshat' :15, 'nikhil' : 1, 'me' : 56}

# printing initial json
print ("initial 1st dictionary", ini_dict1)
print ("initial 2nd dictionary", ini_dict2)

# intersecting two dictionaries
final_dict = {x:ini_dict1[x] for x in ini_dict1 
                              if x in ini_dict2}

# printing final result
print ("final dictionary", str(final_dict))
```

**Output:**

> 初始第一字典{'vashu': 5，' manjeet': 10，' nikhil': 1，' akshat': 15}
> 初始第二字典{'nikhil': 1，' me': 56，' akshat': 15}
> 最终字典{'nikhil': 1，' akshat': 15}

**方法 2:使用`& operator`**

```py
# Python code to demonstrate
# intersection of two dictionaries 
# using dict comprehension

# inititialising dictionary
ini_dict1 = {'nikhil': 1, 'vashu' : 5,
             'manjeet' : 10, 'akshat' : 15}
ini_dict2 = {'akshat' :15, 'nikhil' : 1, 'me' : 56}

# printing initial json
print ("initial 1st dictionary", ini_dict1)
print ("initial 2nd dictionary", ini_dict2)

# intersecting two dictionaries
final_dict = dict(ini_dict1.items() & ini_dict2.items())

# printing final result
print ("final dictionary", str(final_dict))
```

**Output:**

> 初始第一字典{'vashu': 5，' manjeet': 10，' nikhil': 1，' akshat': 15}
> 初始第二字典{'nikhil': 1，' akshat': 15，' me': 56}
> 最终字典{'nikhil': 1，' akshat': 15}