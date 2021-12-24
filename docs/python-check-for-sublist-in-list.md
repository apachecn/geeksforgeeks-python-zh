# Python–检查列表中的子列表

> 原文:[https://www . geesforgeks . org/python-检查列表中的子列表/](https://www.geeksforgeeks.org/python-check-for-sublist-in-list/)

有时候，在使用 Python Lists 时，我们可能会遇到一个问题，那就是我们需要检查一个特定的子列表是否以精确的顺序包含在一个列表中。这项任务可以应用于许多领域，如学校编程和网络开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [5，6，3，8，2，1，7，1]，子列表= [8，2，3]
> **输出** : False
> 
> **输入** : test_list = [5，6，3，8，2，3，7，1]，子列表= [8，2，3]
> **输出**:真

**方法#1:使用循环+列表切片**
以上功能的组合可以用来解决这个问题。在本文中，我们使用列表切片技术通过增量切片来执行检查子列表的任务。

```py
# Python3 code to demonstrate working of 
# Check for Sublist in List
# Using loop + list slicing

# initializing list
test_list = [5, 6, 3, 8, 2, 1, 7, 1]

# printing original list 
print("The original list : " + str(test_list))

# initializing sublist 
sublist = [8, 2, 1]

# Check for Sublist in List
# Using loop + list slicing
res = False
for idx in range(len(test_list) - len(sublist) + 1):
        if test_list[idx : idx + len(sublist)] == sublist:
            res = True 
            break

# printing result 
print("Is sublist present in list ? : " + str(res))
```

**Output :**

```py
The original list : [5, 6, 3, 8, 2, 1, 7, 1]
Is sublist present in list ? : True

```

**方法 2:使用`any()` +列表切片+生成器表达式**
以上功能的组合用于解决这个问题。在这种情况下，我们使用 any()执行检查任何等同于所需的子列表的任务，列表切片用于对所需长度的增量列表进行切片。

```py
# Python3 code to demonstrate working of 
# Check for Sublist in List
# Using any() + list slicing + generator expression

# initializing list
test_list = [5, 6, 3, 8, 2, 1, 7, 1]

# printing original list 
print("The original list : " + str(test_list))

# initializing sublist 
sublist = [8, 2, 1]

# Check for Sublist in List
# Using any() + list slicing + generator expression
res = any(test_list[idx : idx + len(sublist)] == sublist
        for idx in range(len(test_list) - len(sublist) + 1))

# printing result 
print("Is sublist present in list ? : " + str(res))
```

**Output :**

```py
The original list : [5, 6, 3, 8, 2, 1, 7, 1]
Is sublist present in list ? : True

```