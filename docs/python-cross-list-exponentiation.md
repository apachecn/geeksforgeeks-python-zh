# Python–交叉列表求幂

> 原文:[https://www . geesforgeks . org/python-跨列表-求幂/](https://www.geeksforgeeks.org/python-cross-list-exponentiation/)

有时我们会遇到这样的情况，我们需要在相似的索引处对两个列表的每个元素应用一个特定的函数。这些非常相似，是作为某些实用程序的应用程序出现的。让我们讨论幂运算的某些方法，即两个列表的余数。

**方法#1:使用`zip()` +列表理解**
可以使用 zip 操作将一个列表与另一个列表链接起来，并且计算部分可以由列表理解来处理，因此提供了这个特定问题的简写。

```py
# Python3 code to demonstrate 
# Cross list exponentiation
# using zip() + list comprehension

# initializing lists 
test_list1 = [3, 5, 2, 6, 4]
test_list2 = [7, 3, 4, 1, 5]

# printing original lists 
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# Cross list exponentiation
# using zip() + list comprehension
res = [i ** j for i, j in zip(test_list1, test_list2)]

# printing result
print ("The cross exponentiation list is : " + str(res))
```

**Output :**

```py
The original list 1 is : [3, 5, 2, 6, 4]
The original list 2 is : [7, 3, 4, 1, 5]
The cross exponentiation list is : [2187, 125, 16, 6, 1024]

```