# Python–向元组列表添加自定义列

> 原文:[https://www . geesforgeks . org/python-add-custom-column-to-tuple-list/](https://www.geeksforgeeks.org/python-add-custom-column-to-tuple-list/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即需要向元组列表中添加自定义列。这种问题可以应用于数据领域，例如 web 开发。让我们讨论执行这项任务的某些方法。

> **输入** :
> 测试 _ 列表= [(3)、(7)、(2)、]
> cus_eles = [7、8、2]
> **输出** : [(3、7)、(7、8)、(2、2)]
> 
> **输入** :
> 测试列表= [(3，9，6，10)]
> cus _ eles =[7]
> T5】输出 : [(3，9，6，10，7)]

**方法#1:使用列表理解+ `zip()`**
以上功能的组合可以用来解决这个问题。在本文中，我们在 zip()的帮助下执行自定义元素和元组的配对。

```
# Python3 code to demonstrate working of 
# Add Custom Column to Tuple list
# Using list comprehension + zip()

# initializing list
test_list = [(3, 4), (78, 76), (2, 3)]

# printing original list
print("The original list is : " + str(test_list))

# initializing add list
cus_eles = [17, 23, 12]

# Add Custom Column to Tuple list
# Using list comprehension + zip()
res = [sub + (val, ) for sub, val in zip(test_list, cus_eles)]

# printing result 
print("The tuples after adding elements : " + str(res)) 
```

**Output :**

```
The original list is : [(3, 4), (78, 76), (2, 3)]
The tuples after adding elements : [(3, 4, 17), (78, 76, 23), (2, 3, 12)]

```

**方法 2:使用`map()`+λ**
以上功能的组合也可以用来解决这个问题。在本例中，我们使用 map()执行将逻辑扩展到每个元组的任务，lambda 用于执行加法任务。

```
# Python3 code to demonstrate working of 
# Add Custom Column to Tuple list
# Using map() + lambda

# initializing list
test_list = [(3, 4), (78, 76), (2, 3)]

# printing original list
print("The original list is : " + str(test_list))

# initializing add list
cus_eles = [17, 23, 12]

# Add Custom Column to Tuple list
# Using map() + lambda
res = list(map(lambda a, b: a +(b, ), test_list, cur_eles))

# printing result 
print("The tuples after adding elements : " + str(res)) 
```

**Output :**

```
The original list is : [(3, 4), (78, 76), (2, 3)]
The tuples after adding elements : [(3, 4, 17), (78, 76, 23), (2, 3, 12)]

```