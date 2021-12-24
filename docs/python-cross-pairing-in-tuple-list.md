# Python–元组列表中的交叉配对

> 原文:[https://www . geesforgeks . org/python-元组列表中的交叉配对/](https://www.geeksforgeeks.org/python-cross-pairing-in-tuple-list/)

给定 2 个元组，执行相应元组的交叉配对，如果两个元组的第一个元素匹配，则转换为单元组。

> **输入** : test_list1 = [(1，7)，(6，7)，(8，100)，(4，21)]，test_list2 = [(1，3)，(2，1)，(9，7)，(2，17)]
> **输出** : [(7，3)]
> **解释** : 1 作为元组元素出现在 pos。1 在两个元组中，它的第二个元素被配对并返回。
> 
> **输入** : test_list1 = [(10，7)，(6，7)，(8，100)，(4，21)]，test_list2 = [(1，3)，(2，1)，(9，7)，(2，17)]
> **输出** : []
> **解释**:不可能配对。

**方法一:使用列表理解**

在本文中，我们使用条件语句和检查第一个元素，并在列表理解中构造新的元组。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Cross Pairing in Tuple List
# Using list comprehension

# initializing lists
test_list1 = [(1, 7), (6, 7), (9, 100), (4, 21)]
test_list2 = [(1, 3), (2, 1), (9, 7), (2, 17)]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# corresponding loop in list comprehension
res = [(sub1[1], sub2[1]) for sub2 in test_list2 for sub1 in test_list1 if sub1[0] == sub2[0]]

# printing result 
print("The mapped tuples : " + str(res))
```

**Output**

```py
The original list 1 : [(1, 7), (6, 7), (9, 100), (4, 21)]
The original list 2 : [(1, 3), (2, 1), (9, 7), (2, 17)]
The mapped tuples : [(7, 3), (100, 7)]

```

**方法二:使用 zip() +列表理解**

在这种情况下，配对任务使用 zip()完成，条件检查在列表理解中完成。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Cross Pairing in Tuple List
# Using zip() + list comprehension

# initializing lists
test_list1 = [(1, 7), (6, 7), (9, 100), (4, 21)]
test_list2 = [(1, 3), (2, 1), (9, 7), (2, 17)]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# zip() is used for pairing 
res = [(a[1], b[1]) for a, b in zip(test_list1, test_list2) if a[0] == b[0]]

# printing result 
print("The mapped tuples : " + str(res))
```

**Output**

```py
The original list 1 : [(1, 7), (6, 7), (9, 100), (4, 21)]
The original list 2 : [(1, 3), (2, 1), (9, 7), (2, 17)]
The mapped tuples : [(7, 3), (100, 7)]

```