# Python |用列表值分配多个变量

> 原文:[https://www . geesforgeks . org/python-赋值-带列表值的多变量/](https://www.geeksforgeeks.org/python-assign-multiple-variables-with-list-values/)

我们通常完成获取某些索引值并从中分配变量的任务。我们遵循的一般方法是通过索引提取每个列表元素，然后将其分配给变量。这种方法需要更多的代码行。让我们讨论以紧凑的方式完成这项任务的某些方法，以提高可读性。

**方法#1:使用列表理解**
通过使用列表理解，人们可以轻松地在一行中完成这项任务。我们为 RHS 中的特定索引运行一个循环，并将它们分配给所需的变量。

```py
# Python3 code to demonstrate 
# to assign variables from list element
# using list comprehension 

# initializing list  
test_list = [1, 4, 5, 6, 7, 3]

# printing original list
print ("The original list is : " + str(test_list))

# using list comprehension
# to assign variables from list element
var1, var2, var3 = [test_list[i] for i in (1, 3, 5)]

# printing result
print ("The variables are : " +  str(var1) + 
                           " " + str(var2) +
                            " " + str(var3))
```

**Output:**

```py
The original list is : [1, 4, 5, 6, 7, 3]
The variables are : 4 6 3

```