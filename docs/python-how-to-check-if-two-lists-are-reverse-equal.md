# Python–如何检查两个列表是否反向相等

> 原文:[https://www . geesforgeks . org/python-如何检查两个列表是否反向相等/](https://www.geeksforgeeks.org/python-how-to-check-if-two-lists-are-reverse-equal/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要检查两个列表是否彼此相反。这类问题可以应用于许多领域，如日常编程和学校编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_list1 = [5，6，7]，test_list2 = [7，6，5]
> **输出**:真
> 
> **输入** : test_list1 = [5，6]，test_list2 = [7，6]
> **输出**:假

**方法#1:使用`reversed() and "==" operator`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 reversed()执行反转任务，并使用“==”运算符测试相等性。

```
# Python3 code to demonstrate working of 
# Check if two lists are reverse equal
# Using reversed() + == operator

# initializing lists
test_list1 = [5, 6, 7, 8]
test_list2 = [8, 7, 6, 5]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Check if two lists are reverse equal
# Using reversed() + == operator
res = test_list1 == list(reversed(test_list2))

# printing result 
print("Are both list reverse of each other ? : " + str(res))
```

**Output :**

```
The original list 1 : [5, 6, 7, 8]
The original list 2 : [8, 7, 6, 5]
Are both list reverse of each other ? : True

```

**方法 2:使用列表切片+ "= "运算符**
这是解决这个问题的又一种方法。在这种情况下，我们使用切片技术执行列表反转任务。

```
# Python3 code to demonstrate working of 
# Check if two lists are reverse equal
# Using list slicing + "==" operator

# initializing lists
test_list1 = [5, 6, 7, 8]
test_list2 = [8, 7, 6, 5]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Check if two lists are reverse equal
# Using list slicing + "==" operator
res = test_list1 == test_list2[::-1]

# printing result 
print("Are both list reverse of each other ? : " + str(res))
```

**Output :**

```
The original list 1 : [5, 6, 7, 8]
The original list 2 : [8, 7, 6, 5]
Are both list reverse of each other ? : True

```