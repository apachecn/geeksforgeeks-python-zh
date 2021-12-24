# Python |元组的列求和

> 原文:[https://www . geeksforgeeks . org/python-列-元组求和/](https://www.geeksforgeeks.org/python-column-summation-of-tuples/)

有时，我们会遇到一个问题，我们处理一个复杂类型的矩阵列求和，其中我们被赋予一个元组，我们需要对它的相似元素执行求和。这在机器学习领域有很好的应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`zip()` +列表理解**
这个问题可以通过使用列表理解来解决，该列表理解可以执行列求和逻辑，并且作为结果以及在垂直求和时使用 zip 函数来绑定元素。

```
# Python3 code to demonstrate
# column summation of list of tuple
# using list comprehension + zip()

# initializing list 
test_list = [[(1, 4), (2, 3), (5, 2)],
             [(3, 7), (1, 9), (10, 5)]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + zip()
# columnn summation of list of tuple
res = [tuple(sum(j) for j in zip(*i))
            for i in zip(*test_list)]

# print result
print("The summation of columns of tuple list : " + str(res))
```

**Output :**

```
The original list : [[(1, 4), (2, 3), (5, 2)], [(3, 7), (1, 9), (10, 5)]]
The summation of columns of tuple list : [(4, 11), (3, 12), (15, 7)]

```