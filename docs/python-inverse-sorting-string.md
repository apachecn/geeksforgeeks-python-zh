# Python |逆排序字符串

> 原文:[https://www . geesforgeks . org/python-逆向-排序-字符串/](https://www.geeksforgeeks.org/python-inverse-sorting-string/)

有时，在参与竞争性编程测试时，我们可能会遇到这样一个问题，即我们需要按索引以相反的顺序对一对进行排序。这篇特别的文章着重于解决一个问题，在这个问题中，我们需要按降序对数字进行排序，然后按升序对字符串进行排序。这是配对排序中常见的问题类型。让我们讨论一下解决这个问题的方法。

**方法:使用`sorted()`+λ**
这些功能的组合可以用来执行这个任务。在这种情况下，我们将这些值的负值传递给 lambda 函数，这样递增的数字顺序就被认为是递减的，从而成功地完成了这个任务。

```py
# Python3 code to demonstrate working of
# Inverse sorting String, Integer tuple list
# Using sorted() + lambda

# initializing list
test_list = [("Geeks", 5), ("For", 3), ("Geeks", 6), ("Is", 5), 
             ("Best", 7 ), ("For", 5), ("CS", 3)]

# printing original list
print("The original list is : " + str(test_list))

# Inverse sorting String, Integer tuple list
# Using sorted() + lambda
res = sorted(test_list, key = lambda sub: (-sub[1], sub[0]))

# printing result 
print("The list after inverse sorted tuple elements : " + str(res))
```

**Output :**

> 原列表为:[('Geeks '，5)、(' For '，3)、(' Geeks '，6)、(' is '，5)、(' Best '，7)、(' For '，5)、(' CS '，3)]
> 逆序排序后的列表元组元素:[('Best '，7)、(' Geeks '，6)、(' For '，5)、(' Geeks '，5)、(' Is '，5)、(' CS '，3)、(' For '，3)】