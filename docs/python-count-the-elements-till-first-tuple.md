# Python |计算元素直到第一个元组

> 原文:[https://www . geesforgeks . org/python-count-the-elements-to-first-tuple/](https://www.geeksforgeeks.org/python-count-the-elements-till-first-tuple/)

有时，在处理记录时，我们可能会遇到一个问题，记录的一个元素是另一个元组记录，我们可能必须计算记录之前出现的元素计数。这是一个不常发生的问题，但是有一个解决方法是有用的。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `isintance() + enumerate()`**
使用上述功能可以解决这个问题。在这种情况下，我们只需使用`enumerate()`循环遍历元素以获取其索引计数，并使用`isinstance()`检查类型。

```py
# Python3 code to demonstrate working of
# Elements till first tuple
# using isinstance() + enumerate() + loop

# initialize tuple
test_tup = (1, 5, 7, (4, 6), 10)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Elements till first tuple
# using isinstance() + enumerate() + loop
for count, ele in enumerate(test_tup):
    if isinstance(ele, tuple):
        break

# printing result
print("Elements till the first tuple : " + str(count))
```

**Output :**

```py
The original tuple : (1, 5, 7, (4, 6), 10)
Elements till the first tuple : 3

```