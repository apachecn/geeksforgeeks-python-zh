# Python–在两个元组列表中找到相似索引的最大值

> 原文:[https://www . geesforgeks . org/python-在元组列表中找到最大相似索引数/](https://www.geeksforgeeks.org/python-find-the-maximum-of-similar-indices-in-two-list-of-tuples/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，需要对元组列表执行交叉最大化。这种应用在 web 开发领域非常流行。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `zip()`**
上述功能的组合可用于执行该特定任务。在本文中，我们使用列表理解来遍历列表，并在 zip()的帮助下实现跨列表的最大化。

```
# Python3 code to demonstrate working of
# Maximum of Tuple List Similar Indices
# using list comprehension + zip()

# initialize lists
test_list1 = [(2, 4), (6, 7), (5, 1)]
test_list2 = [(5, 4), (8, 10), (8, 14)]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Maximum of Tuple List Similar Indices
# using list comprehension + zip()
res = [(max(x[0], y[0]), max(x[1], y[1])) 
       for x, y in zip(test_list1, test_list2)]

# printing result
print("The Maximum across lists is : " + str(res))
```

**Output :**

```
The original list 1 : [(2, 4), (6, 7), (5, 1)]
The original list 2 : [(5, 4), (8, 10), (8, 14)]
The Maximum across lists is : [(5, 4), (8, 10), (8, 14)]

```