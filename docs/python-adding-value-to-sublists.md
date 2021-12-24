# Python |给子列表增加价值

> 原文:[https://www . geeksforgeeks . org/python-子列表增值/](https://www.geeksforgeeks.org/python-adding-value-to-sublists/)

有时，我们只需要通过向所有子列表附加一个相似的值来操作列表列表。使用循环来完成这个特殊的任务可能是一种选择，但是有时会牺牲代码的可读性。人们总是希望有一个人来完成这项特殊的任务。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
列表理解可以使用类似的循环构造来执行这个特定的任务，但是只需一行。这增加了代码的可读性。

```
# Python3 code to demonstrate 
# appending single value 
# using list comprehension 

# initializing list of lists
test_list = [[1, 3], [3, 4], [6, 5], [4, 5]]

# printing original list 
print("The original list : " +  str(test_list))

# declaring element to be inserted
K = "GFG"

# using list comprehension 
# appending single value
res = [[i, j, K ] for i, j in test_list]

# printing result 
print("The list after adding element :  " + str(res))
```

**Output :**

> 原列表:[[1，3]，[3，4]，[6，5]，[4，5]]
> 添加元素后的列表:[[1，3，' GFG']，[3，4，' GFG']，[6，5，' GFG']，[4，5，' GFG']]