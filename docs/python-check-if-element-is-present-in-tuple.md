# Python |检查元组中是否存在元素

> 原文:[https://www . geesforgeks . org/python-检查元组中是否存在元素/](https://www.geeksforgeeks.org/python-check-if-element-is-present-in-tuple/)

有时，在处理数据时，我们会遇到一个问题，即我们需要检查正在处理的数据是否有特定的元素。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是执行这个任务的蛮力方法。在这种情况下，我们遍历元组，检查每个元素是否是我们的，如果找到，我们返回真。

```py
# Python3 code to demonstrate working of
# Check if element is present in tuple
# using loop

# initialize tuple
test_tup = (10, 4, 5, 6, 8)

# printing original tuple
print("The original tuple : " + str(test_tup))

# initialize N 
N = 6

# Check if element is present in tuple
# using loop
res = False 
for ele in test_tup :
    if N == ele :
        res = True
        break

# printing result
print("Does tuple contain required value ? : " + str(res))
```

**Output :**

```py
The original tuple : (10, 4, 5, 6, 8)
Does tuple contain required value ? : True

```