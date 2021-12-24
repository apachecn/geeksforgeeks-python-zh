# Python |检查范围出现的元素

> 原文:[https://www . geesforgeks . org/python-check-element-for-range-occurrence/](https://www.geeksforgeeks.org/python-check-element-for-range-occurrence/)

有时，在处理数据时，我们会遇到一个简单的问题，即我们有元组形式的范围，我们需要检查特定的数字是否位于元组建议的任何范围之间。这在竞争性编程中有它的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `enumerate()`**
该任务可以使用上述功能的组合来执行。在这种情况下，我们只需要遍历列表的每个元素，并使用`enumerate()`返回元素存在的元组对的索引。

```py
# Python3 code to demonstrate working of
# Check element for range occurrence
# Using loop + enumerate()

# Initializing list
test_list = [(45, 90), (100, 147), (150, 200)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing element
N = 124

# Check element for range occurrence
# Using loop + enumerate()
res = None
for idx in (idx for idx, (sec, fir) in enumerate(test_list) if sec <= N <= fir):
    res = idx

# printing result
print("The index of tuple between which element occurs : " + str(res))
```

**Output :**

```py
The original list is : [(45, 90), (100, 147), (150, 200)]
The index of tuple between which element occurs : 1

```