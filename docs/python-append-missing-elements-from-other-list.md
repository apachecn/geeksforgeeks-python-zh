# Python–追加其他列表中缺失的元素

> 原文:[https://www . geesforgeks . org/python-append-missing-elements-from-other-list/](https://www.geeksforgeeks.org/python-append-missing-elements-from-other-list/)

给定两个列表，将列表 1 中缺少的元素追加到列表 2 中。

> **输入** : test_list1 = [5，6，4，8，9，1]，test_list2 = [9，8，10]
> **输出** : [5，6，4，1，9，8，10]
> **解释**:列表 2 中依次增加了 5，6，4，1。
> 
> **输入** : test_list1 = [5，6，4，8，9，1]，test_list2 = [9，10]
> **输出** : [5，6，4，8，1，9，10]
> **解释**:列表 2 中依次增加了 5，6，4，8，1。

**方法一:使用列表理解**

在这种情况下，我们迭代列表 1 来检查列表 2 中缺少的元素，然后将这些元素添加到列表 2 中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Append Missing elements from other List
# Using list comprehension

# initializing list
test_list1 = [5, 6, 4, 8, 9, 1]
test_list2 = [9, 8, 7]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# extracting elements from list 1 which are not in list 2
temp1 = [ele for ele in test_list1 if ele not in test_list2]

# constructing result 
res = temp1 + test_list2

# printing result 
print("The modified list 2 : " + str(res))
```

**Output**

```py
The original list 1 is : [5, 6, 4, 8, 9, 1]
The original list 2 is : [9, 8, 7]
The modified list 2 : [5, 6, 4, 1, 9, 8, 7]

```

**方法 2:使用 set()+“-”运算符+ extend()**

在本例中，我们使用 set()和–operator 检查列表 2 中缺少的列表 1 的元素，并使用 extend()连接这两个列表以获得所需的结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Append Missing elements from other List
# Using set() + "-" operator + extend()

# initializing list
test_list1 = [5, 6, 4, 8, 9, 1]
test_list2 = [9, 8, 7]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# finding missing words
rem_list = (set(test_list1) - set(test_list2))

# checking order
res = [ele for ele in test_list1 if ele in rem_list] 

# joining result
res.extend(test_list2)

# printing result 
print("The modified list 2 : " + str(res))
```

**Output**

```py
The original list 1 is : [5, 6, 4, 8, 9, 1]
The original list 2 is : [9, 8, 7]
The modified list 2 : [5, 6, 4, 1, 9, 8, 7]

```