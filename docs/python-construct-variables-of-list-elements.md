# Python–构造列表元素的变量

> 原文:[https://www . geeksforgeeks . org/python-构造-变量-元素列表/](https://www.geeksforgeeks.org/python-construct-variables-of-list-elements/)

有时候，在使用 python 列表时，我们会遇到一个问题，我们需要将列表中的每个元素转换为变量，并将相应的列表转换为值。这可以应用于许多领域，如网页开发和日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用`dict() + zip()`**
上述功能的组合可用于执行该任务。在这种情况下，我们将列表压缩到字典中，字典的键可以作为变量，值可以作为变量值。

```
# Python3 code to demonstrate 
# Construct variables of list elements
# using dict() + zip()

# Initializing lists 
test_list1 = ['gfg', 'is', 'best']
test_list2 = [1, 2, 3]

# printing original lists 
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Construct variables of list elements
# using dict() + zip()
res = dict(zip(test_list1, test_list2))

# printing result 
print ("Variable value 1 : " + str(res['gfg']))
print ("Variable value 2 : " + str(res['best']))
```

**Output :**

```
The original list 1 is : ['gfg', 'is', 'best']
The original list 2 is : [1, 2, 3]
Variable value 1 : 1
Variable value 2 : 3

```