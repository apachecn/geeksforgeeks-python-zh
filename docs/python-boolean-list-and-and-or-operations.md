# Python |布尔列表 AND 和 OR 运算

> 原文:[https://www . geesforgeks . org/python-boolean-list-and-and-or-operations/](https://www.geeksforgeeks.org/python-boolean-list-and-and-or-operations/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们有一个布尔列表，我们需要找到其中所有元素的布尔“与”或“或”。这类问题在数据科学领域有应用。让我们讨论一个简单的方法来解决这两个任务。

**方法#1:与运算–使用`all()`**
这个问题的解决方案非常简单，但是需要应用意识。all()执行列表的布尔“与”运算并返回结果。

```
# Python3 code to demonstrate working of
# Boolean List AND and OR operations
# AND Operation - Using all()

# initialize list
test_list = [True, True, False, True, False]

# printing original list
print("The original list is : " + str(test_list))

# Boolean List AND and OR operations
# AND Operation - Using all()
res = all(test_list)

# printing result
print("Result after performing AND among elements : " + str(res))
```

**Output :**

```
The original list is : [True, True, False, True, False]
Result after performing AND among elements : False

```