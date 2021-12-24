# Python–从列表中获取偶数元素的索引

> 原文:[https://www . geesforgeks . org/python-get-indexs-of-even-elements-from-list/](https://www.geeksforgeeks.org/python-get-indices-of-even-elements-from-list/)

有时候，在使用 Python 列表时，我们可能会遇到一个问题，我们希望找到偶数元素。这项工作可以在许多领域进行，例如网页开发和使用数据库。我们有时可能需要找到它们的索引。让我们讨论寻找偶元素的指数的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，我们检查列表中的偶数元素，并相应地附加其索引。

```
# Python3 code to demonstrate working of
# Even Elements indices
# using loop

# initialize list
test_list = [5, 6, 10, 4, 7, 1, 19]

# printing original list
print("The original list is : " + str(test_list))

# Even Elements indices
# using loop
res = []
for idx, ele in enumerate(test_list):
    if ele % 2 == 0:
        res.append(idx)

# printing result
print("Indices list Even elements is : " + str(res))
```

**Output :**

```
The original list is : [5, 6, 10, 4, 7, 1, 19]
Indices list Even elements is : [1, 2, 3]

```