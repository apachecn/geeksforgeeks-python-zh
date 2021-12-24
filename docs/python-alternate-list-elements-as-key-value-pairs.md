# Python–作为键值对的替代列表元素

> 原文:[https://www . geesforgeks . org/python-alternate-list-elements-as-key-value-pairs/](https://www.geeksforgeeks.org/python-alternate-list-elements-as-key-value-pairs/)

给定一个列表，通过将替换元素映射为键值对将其转换为字典。

> **输入** : test_list = [2，3，5，6，7，8]
> **输出** : {3: 6，6: 8，2: 5，5: 7}
> **解释**:映射得到键值对的替换元素。3 - > 6【候补】
> 
> **输入** : test_list = [2，3，5，6]
> **输出** : {3: 6，2: 5}
> **解释**:映射得到键值对的替换元素。3 - > 6【候补】

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们迭代两次以获得两个可选元素，从而获得所需的所有可选键值字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Alternate Elements Dictionary
# Using loop

# initializing list
test_list = [2, 3, 5, 6, 7, 8, 9, 10] 

# printing original list
print("The original list is : " + str(test_list))

res = dict()

# pairing first set of Alternate elements 
for idx in range(len(test_list) - 2):
    if idx % 2:
        res[test_list[idx]] = test_list[idx + 2]

# pairing other set
for idx in range(len(test_list) - 2):
    if not idx % 2:
        res[test_list[idx]] = test_list[idx + 2]

# printing result 
print("The extracted dictionary : " + str(res))
```

**Output**

```
The original list is : [2, 3, 5, 6, 7, 8, 9, 10]
The extracted dictionary : {3: 6, 6: 8, 8: 10, 2: 5, 5: 7, 7: 9}

```

**方法二:使用词典理解+列表切片**

这是执行这项任务的另一种方式。在本文中，我们将两个替换元素列表都切掉，并使用字典理解进行配对。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Alternate Elements Dictionary
# Using dictionary comprehension + list slicing 

# initializing list
test_list = [2, 3, 5, 6, 7, 8, 9, 10] 

# printing original list
print("The original list is : " + str(test_list))

# extracting lists
list1 = test_list[1::2]
list2 = test_list[::2]

# constructing pairs using dictionary comprehension
res = {list1[idx] : list1[idx + 1] for idx in range(len(list1) - 1)}
res.update({list2[idx] : list2[idx + 1] for idx in range(len(list2) - 1)})

# printing result 
print("The extracted dictionary : " + str(res))
```

**Output**

```
The original list is : [2, 3, 5, 6, 7, 8, 9, 10]
The extracted dictionary : {3: 6, 6: 8, 8: 10, 2: 5, 5: 7, 7: 9}

```