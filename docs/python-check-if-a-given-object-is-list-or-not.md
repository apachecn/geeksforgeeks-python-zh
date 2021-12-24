# Python |检查给定对象是否在列表中

> 原文:[https://www . geesforgeks . org/python-检查给定对象是否在列表中/](https://www.geeksforgeeks.org/python-check-if-a-given-object-is-list-or-not/)

给定一个对象，任务是检查该对象是否在列表中。

**方法 1:使用*是*还是**

```
# Python code to demonstrate
# check whether the object 
# is a list or not

# initialisation list
ini_list1 = [1, 2, 3, 4, 5]
ini_list2 = '12345'

# code to check whether
# object is a list or not
if isinstance(ini_list1, list):
  print("your object is a list !")
else:
    print("your object is not a list")

if isinstance(ini_list2, list):
    print("your object is a list")
else:
    print("your object is not a list")
```

**Output:**

```
your object is a list !
your object is not a list

```

**方法 2:使用`type(x)`**

```
# Python code to demonstrate
# check whether object 
# is a list or not

# initialisation list
ini_list1 = [1, 2, 3, 4, 5]
ini_list2 = (12, 22, 33)

# code to check whether
# object is a list or not
if type(ini_list1) is list:
    print("your object is a list")
else:
    print("your object is not a list")

if type(ini_list2) is list:
    print("your object is a list")
else:
    print("your object is not a list")
```

**Output:**

```
your object is a list
your object is not a list

```