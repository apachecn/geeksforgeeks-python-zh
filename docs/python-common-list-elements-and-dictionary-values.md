# Python–常用列表元素和字典值

> 原文:[https://www . geesforgeks . org/python-common-list-elements-and-dictionary-values/](https://www.geeksforgeeks.org/python-common-list-elements-and-dictionary-values/)

给定列表和字典，提取列表和字典值的公共元素。

> **输入**:test _ list =[“Gfg”，“is”，“Best”，“For”]，subs _ dict = { 4:“Gfg”，8:“Geeks”，9:“Good”，}
> **输出**:[‘Gfg’]
> **解释**:“Gfg”在列表和字典值中都很常见。
> **输入**:test _ list =[“Gfg”、“is”、“Best”、“For”、“Geeks”]，subs _ dict = { 4:“Gfg”，8:“Geeks”，9:“Best”，}
> **输出**:[“Gfg”、“Geeks”、“Best”]
> **解释**:提取 3 个常用值。

**方法#1:使用列表理解+值()**

上述功能的组合提供了一种可以在一行中执行该任务的方式。在本文中，我们使用 values()提取字典的值，并使用列表理解来执行迭代和交集检查。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# List elements and dictionary values intersection
# Using list comprehension + values()

# initializing list
test_list = ["Gfg", "is", "Best", "For", "Geeks"]

# printing original list
print("The original list : " + str(test_list))

# initializing subs. Dictionary
subs_dict = {4 : "Gfg", 8 : "Geeks", 9 : " Good", }

# Intersection of elements, using "in" for checking presence
res = [ele for ele in test_list if ele in subs_dict.values()]

# printing result
print("Intersection elements : " + str(res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Best', 'For', 'Geeks']
Intersection elements : ['Gfg', 'Geeks']
```

**方法 2:使用 set() +交集()**

在这种方法中，列表和字典值都被转换为 set()，然后执行交集以获得公共元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Common list elements and dictionary values
# Using set() and intersection()

# initializing list
test_list = ["Gfg", "is", "Best", "For", "Geeks"]

# printing original list
print("The original list : " + str(test_list))

# initializing subs. Dictionary
subs_dict = {4 : "Gfg", 8 : "Geeks", 9 : " Good", }

# Intersection of elements, using set() to convert
# intersection() for common elements
res = list(set(test_list).intersection(list(subs_dict.values())))

# printing result
print("Intersection elements : " + str(res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Best', 'For', 'Geeks']
Intersection elements : ['Geeks', 'Gfg']
```