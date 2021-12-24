# Python–用列表展平词典

> 原文:[https://www . geesforgeks . org/python-flat-dictionary-with-list/](https://www.geeksforgeeks.org/python-flatten-dictionary-with-list/)

给定一个列表和字典，在列表中键的可用元素的位置展平带有键和值的字典。

> **输入**:test _ list =[“Gfg”、“is”、“Best”、“For”、“Geeks”]，subs _ dict = {“Gfg”:7 }
> **输出**:[‘Gfg’，7，‘is’，‘Best’，‘For’，‘Geeks’]
> **解释**:“Gfg”被替换，后面是它在字典中的值。
> 
> **输入**:test _ list =[“Gfg”、“is”、“Best”、“For”、“Geeks”]，subs _ dict = {“Gfg”:7、“Best”:8 }
> **输出**:【‘Gfg’、‘is’、‘Best’、‘For’、‘Geeks’】
> **解释**:无替换。没有匹配的值。

**方法一:使用列表理解+ get()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 get()附加所有的键(如果存在的话)以及列表中的值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Flatten Dictionary with List
# Using get() + list comprehension

# initializing list
test_list = ["Gfg", "is", "Best", "For", "Geeks"]

# printing original list
print("The original list : " + str(test_list))

# initializing subs. Dictionary
subs_dict = {"Gfg" : 7, "Geeks" : 8}

# get() to perform presence checks and assign value
temp = object()
res = [ele for sub in ((ele, subs_dict.get(ele, temp))
       for ele in test_list) for ele in sub if ele != temp]

# printing result 
print("The list after substitution : " + str(res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Best', 'For', 'Geeks']
The list after substitution : ['Gfg', 7, 'is', 'Best', 'For', 'Geeks', 8]

```

**方法 2:使用 chain.from_iterable() +列表理解**

这是执行这项任务的另一种方式。在这种情况下，我们形成键值对列表，如果存在就追加，如果不存在就保留元素。接下来，使用 chain.from_iterable()执行键值列表的展平。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Flatten Dictionary with List
# Using chain.from_iterable() + list comprehension 
from itertools import chain

# initializing list
test_list = ["Gfg", "is", "Best", "For", "Geeks"]

# printing original list
print("The original list : " + str(test_list))

# initializing subs. Dictionary
subs_dict = {"Gfg" : 7, "Geeks" : 8}

temp = ([ele, subs_dict[ele]] if ele in subs_dict 
                  else [ele] for ele in test_list)

# chain.from_iterable() for flattening 
res = list(chain.from_iterable(temp))

# printing result 
print("The list after substitution : " + str(res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Best', 'For', 'Geeks']
The list after substitution : ['Gfg', 7, 'is', 'Best', 'For', 'Geeks', 8]

```