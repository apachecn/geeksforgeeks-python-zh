# 列表中 Python–K 差异索引配对

> 原文:[https://www . geesforgeks . org/python-k-difference-index-pairing-in-list/](https://www.geeksforgeeks.org/python-k-difference-index-pairing-in-list/)

有时候在编程的时候，我们会面临一个问题，那就是我们需要执行 K 个差分元素的拼接。这个问题可能发生在学校编程或竞争性编程的时候。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+ `zip()`**
结合以上功能可以解决这个问题。在本文中，我们使用列表理解来迭代列表，并使用 zip()来形成对。

```py
# Python3 code to demonstrate working of
# K difference index pairing in list
# using list comprehension + zip()

# initialize list 
test_list = ["G", "F", "G", "I", "S", "B", "E", "S", "T"]

# printing original list 
print("The original list : " + str(test_list))

# initialize K
K = 3

# K difference index pairing in list
# using list comprehension + zip()
res = [i + j for i, j in zip(test_list, test_list[K :])]

# printing result
print("List after K difference concatenation is : " + str(res))
```

**Output :**

```py
The original list : ['G', 'F', 'G', 'I', 'S', 'B', 'E', 'S', 'T']
List after K difference concatenation is : ['GI', 'FS', 'GB', 'IE', 'SS', 'BT']

```