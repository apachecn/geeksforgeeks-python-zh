# Python |从给定词典中按排序顺序获取项目

> 原文:[https://www . geeksforgeeks . org/python-按给定字典中的排序顺序获取项目/](https://www.geeksforgeeks.org/python-get-items-in-sorted-order-from-given-dictionary/)

给定一个字典，任务是按排序顺序从字典中获取所有项目。让我们讨论一下完成这项任务的不同方法。

**方法一:使用`sorted()`**

```py
# Python code to demonstrate
# to get sorted items from dictionary

# initialising _dictionary
ini_dict = {'a' : 'akshat', 'b' : 'bhuvan', 'c': 'chandan'}

# printing iniial_dictionary
print ("iniial_dictionary", str(ini_dict))

# getting items in sorted order
print ("\nItems in sorted order")
for key in sorted(ini_dict):
    print (ini_dict[key])
```

**输出:**

```py
iniial_dictionary {'b': 'bhuvan', 'c': 'chandan', 'a': 'akshat'}

Items in sorted order
akshat
bhuvan
chandan

```