# Python |元组列表中的自定义排序

> 原文:[https://www . geesforgeks . org/python-自定义-元组列表中的排序/](https://www.geeksforgeeks.org/python-custom-sorting-in-list-of-tuples/)

有时，在处理元组列表时，我们可能会遇到需要执行排序的问题。朴素排序更容易，但有时，我们必须执行自定义排序，即通过减少第一个元素的顺序和增加第二个元素的顺序。这些也可以是不同类型的元组。让我们讨论执行这种自定义排序的某些情况和解决方案。

**方法#1:使用`sorted()` + lambda**
该任务可以使用上述功能的组合来执行。在这种情况下，我们只执行正常的排序，但是另外我们提供一个 lambda 函数来处理上面讨论的自定义排序的情况。

```py
# Python3 code to demonstrate working of
# Custom sorting in list of tuples
# Using sorted() + lambda

# Initializing list
test_list = [(7, 8), (5, 6), (7, 5), (10, 4), (10, 1)]

# printing original list
print("The original list is : " + str(test_list))

# Custom sorting in list of tuples
# Using sorted() + lambda
res = sorted(test_list, key = lambda sub: (-sub[0], sub[1]))

# printing result
print("The tuple after custom sorting is : " + str(res))
```

**Output :**

```py
The original list is : [(7, 8), (5, 6), (7, 5), (10, 4), (10, 1)]
The tuple after custom sorting is : [(10, 1), (10, 4), (7, 5), (7, 8), (5, 6)]

```