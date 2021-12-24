# Python |检查列表列表中是否存在元素

> 原文:[https://www . geesforgeks . org/python-检查列表中是否存在元素/](https://www.geeksforgeeks.org/python-check-if-element-exists-in-list-of-lists/)

给定一个列表列表，任务是确定给定元素是否存在于任何子列表中。下面给出了一些解决给定任务的方法。

**方法#1:使用任意()**

`any()`每当给定迭代器中出现特定元素时，方法返回 true。

```
# Python code to demonstrate
# finding whether element
# exists in listof list

# initialising nested lists
ini_list = [[1, 2, 5, 10, 7],
            [4, 3, 4, 3, 21],
            [45, 65, 8, 8, 9, 9]]

elem_to_find = 8
elem_to_find1 = 0

# element exists in listof listor not?
res1 = any(elem_to_find in sublist for sublist in ini_list)
res2 = any(elem_to_find1 in sublist for sublist in ini_list)

# printing result
print(str(res1), "\n", str(res2))
```

**Output:**

```
True 
 False

```