# Python |展平给定的词典列表

> 原文:[https://www . geesforgeks . org/python-flat-给定词典列表/](https://www.geeksforgeeks.org/python-flatten-given-list-of-dictionaries/)

给定一个字典列表，任务是将其转换为单个字典，即展平字典列表。
下面给出了几种解决给定任务的方法。
**方法#1:使用天真方法**

## 蟒蛇 3

```py
# Python code to demonstrate
# to flatten list of dictionaries

# Initialising dictionary
ini_dict = [{'a':1}, {'b':2}, {'c':3}]

# printing initial dictionary
print ("initial dictionary", str(ini_dict))

# code to flatten list of dictionary
res = {}
for d in ini_dict:
    res.update(d)

# printing result
print ("result", str(res))
```

**Output:** 

```py
initial dictionary [{'a': 1}, {'b': 2}, {'c': 3}]
result {'b': 2, 'a': 1, 'c': 3}
```

**方法 2:使用字典理解**

## 蟒蛇 3

```py
# Python code to demonstrate
# to flatten list of dictionaries

# Initialising dictionary
ini_dict = [{'a':1}, {'b':2}, {'c':3}]

# printing initial dictionary
print ("initial dictionary", str(ini_dict))

# code to flatten list of dictionary
res = {k: v for d in ini_dict for k, v in d.items()}

# printing result
print ("result", str(res))
```

**Output:** 

```py
initial dictionary [{'a': 1}, {'b': 2}, {'c': 3}]
result {'a': 1, 'c': 3, 'b': 2}
```

**方法三:利用** ***减少***

## 蟒蛇 3

```py
# Python code to demonstrate
# to flatten list of dictionaries
from functools import reduce

# Initialising dictionary
ini_dict = [{'a':1}, {'b':2}, {'c':3}]

# printing initial dictionary
print ("initial dictionary", str(ini_dict))

# code to flatten list of dictionary
res = reduce(lambda d, src: d.update(src) or d, ini_dict, {})

# printing result
print ("result", str(res))
```

**Output:** 

```py
initial dictionary [{'a': 1}, {'b': 2}, {'c': 3}]
result {'a': 1, 'c': 3, 'b': 2}
```

**方法#4:使用集合。**链图

## 蟒蛇 3

```py
# Python code to demonstrate
# to flatten list of
# dictionaries

from collections import ChainMap

# Initialising dictionary
ini_dict = [{'a':1}, {'b':2}, {'c':3}]

# printing initial dictionary
print ("initial dictionary", str(ini_dict))

# code to flatten list of dictionary
res = ChainMap(*ini_dict)

# printing result
print ("result", str(res))
```

**Output:** 

```py
initial dictionary [{'a': 1}, {'b': 2}, {'c': 3}]
result ChainMap({'a': 1}, {'b': 2}, {'c': 3})
```