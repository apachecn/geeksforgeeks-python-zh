# Python |提取相似索引元素

> 原文:[https://www . geesforgeks . org/python-extract-相似-index-elements/](https://www.geeksforgeeks.org/python-extract-similar-index-elements/)

有时，在使用 Python 数据时，我们可能会遇到一个问题，即我们需要跨具有相似索引值的多个列表提取值。这种问题可能出现在许多领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 loop + `zip()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 zip 提取并组合索引元素，然后使用循环中的条件语句提取并检查相似性。

```py
# Python3 code to demonstrate working of
# Extracting similar index elements
# using loop + zip()

# initialize lists
test_list1 = ["a", "b", "c", "d"]
test_list2 = ["g", "b", "s", "d"]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Extracting similar index elements
# using loop + zip()
res = []
for i, j in zip(test_list1, test_list2):
    if i == j:
        res.append(i)

# printing result
print("Similar index elements in lists : " + str(res))
```

**Output :**

```py
The original list 1 : ['a', 'b', 'c', 'd']
The original list 2 : ['g', 'b', 's', 'd']
Similar index elements in lists : ['b', 'd']

```