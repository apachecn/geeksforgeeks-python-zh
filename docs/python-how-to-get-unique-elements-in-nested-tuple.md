# Python |如何获取嵌套元组中的唯一元素

> 原文:[https://www . geesforgeks . org/python-如何获取嵌套元组中的唯一元素/](https://www.geeksforgeeks.org/python-how-to-get-unique-elements-in-nested-tuple/)

有时，在处理元组时，我们可能会遇到这样的问题，即我们有嵌套的元组，并且我们需要提取单独出现的元素，即元素。这种问题在许多领域都有应用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用嵌套循环+ `set()`**
以上 2 个功能可以用来解决这个特殊问题。在这种情况下，我们迭代每个嵌套元组，如果元素第一次出现，就添加到集合中，并在添加之前检查每个元素。

```py
# Python3 code to demonstrate working of
# Unique elements in nested tuple
# Using nested loop + set()

# initialize list
test_list = [(3, 4, 5), (4, 5, 7), (1, 4)]

# printing original list 
print("The original list : " + str(test_list))

# Unique elements in nested tuple
# Using nested loop + set()
res = []
temp = set()
for inner in test_list:
        for ele in inner:
            if not ele in temp:
                temp.add(ele)
                res.append(ele)

# printing result
print("Unique elements in nested tuples are : " + str(res))
```

**Output :**

```py
The original list : [(3, 4, 5), (4, 5, 7), (1, 4)]
Unique elements in nested tuples are : [3, 4, 5, 7, 1]

```