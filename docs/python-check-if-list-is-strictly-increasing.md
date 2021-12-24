# Python |检查列表是否严格增加

> 原文:[https://www . geesforgeks . org/python-检查列表是否严格增加/](https://www.geeksforgeeks.org/python-check-if-list-is-strictly-increasing/)

单调序列的检验是一种效用，在数学中有多种应用，因此与数学相关的每个领域都有应用。由于数学和计算机科学通常是并行的，数学运算，如检查严格递增的序列，可以有助于收集的知识。同样的参数也可以扩展到严格递减列表。让我们讨论执行该测试的某些方法。

**方法#1:使用`all() + zip()`**
`all()`通常会检查输入到其中的所有元素。zip()的任务是从头开始链接列表，从第一个元素开始链接列表，这样就可以对所有元素执行检查。

```
# Python3 code to demonstrate 
# to check for strictly increasing list
# using zip() + all()

# initializing list
test_list = [1, 4, 5, 7, 8, 10]

# printing original lists
print ("Original list : " + str(test_list))

# using zip() + all()
# to check for strictly increasing list
res = all(i < j for i, j in zip(test_list, test_list[1:]))

# printing result
print ("Is list strictly increasing ? : " + str(res))
```

**Output:**

```
Original list : [1, 4, 5, 7, 8, 10]
Is list strictly increasing ? : True

```