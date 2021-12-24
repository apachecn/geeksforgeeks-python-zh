# Python–自定义元素重复

> 原文:[https://www . geesforgeks . org/python-custom-element-repeat/](https://www.geeksforgeeks.org/python-custom-element-repetition/)

给定元素列表和所需的出现列表，执行元素的重复。

> **输入**:test _ list 1 =[“Gfg”、“Best”]，test_list2 = [4，5]
> **输出** : ['Gfg '，' Gfg '，' Gfg '，' Best '，' Best '，' Best '，' Best']
> **解释**:按出现次数重复的元素。
> 
> **输入** : test_list1 = ["Gfg"]，test_list2 = [5]
> **输出** : ['Gfg '，' Gfg '，' Gfg '，' Gfg']
> **解释**:按出现次数重复的元素。

**方法#1:使用循环+扩展()**

上述功能的组合提供了执行该任务的一种方式。在本文中，我们使用循环进行迭代，并使用 extend()重复执行元素的扩展。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Custom elements repetition
# Using  loop + extend()

# initializing lists
test_list1 = ["Gfg", "is", "Best"]
test_list2 = [4, 3, 5]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using loop to perform iteration
res = []
for idx in range(0, len(test_list1)):

    # using extend to perform element repetition
    res.extend([test_list1[idx]] * test_list2[idx])

# printing result 
print("The repeated list : " + str(res))
```

**Output**

```py
The original list 1 : ['Gfg', 'is', 'Best']
The original list 2 : [4, 3, 5]
The repeated list : ['Gfg', 'Gfg', 'Gfg', 'Gfg', 'is', 'is', 'is', 'Best', 'Best', 'Best', 'Best', 'Best']

```

**方法 2:使用 loop + zip()**

这是执行这项任务的另一种方式。在这种情况下，我们使用 zip()将元素与其重复出现匹配，并执行所需的复制任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Custom elements repetition
# Using  loop + zip()

# initializing lists
test_list1 = ["Gfg", "is", "Best"]
test_list2 = [4, 3, 5]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using zip() to intervene elements and occurrence
res = []
for ele, occ in zip(test_list1, test_list2):
    res.extend([ele] * occ)

# printing result 
print("The repeated list : " + str(res))
```

**Output**

```py
The original list 1 : ['Gfg', 'is', 'Best']
The original list 2 : [4, 3, 5]
The repeated list : ['Gfg', 'Gfg', 'Gfg', 'Gfg', 'is', 'is', 'is', 'Best', 'Best', 'Best', 'Best', 'Best']

```