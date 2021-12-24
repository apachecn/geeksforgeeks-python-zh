# Python–从列表

中按第 Kth 个元素过滤元组

> 原文:[https://www . geesforgeks . org/python-filter-元组-by-kth-element-from-list/](https://www.geeksforgeeks.org/python-filter-tuples-by-kth-element-from-list/)

给定元组列表，按列表中第 Kth 个元素的存在进行过滤。

> **输入**:test _ list =[(“GFg”，5，9)、(“is”，4，3)、(“best”，10，29)]，check_list = [4，2，3，10]，K = 2
> **输出**:[(“is”，4，3)]
> **解释** : 3 是第 2 个元素，出现在列表中，因此是过滤后的元组。
> 
> **输入**:test _ list =[(“GFg”，5，9)、(“is”，4，3)、(“best”，10，29)]，check_list = [4，2，3，10]，K = 1
> **输出**:[(“is”，4，3)、(“best”，10，29)]
> **解释** : 4 和 10 是第 1 个元素，出现在列表中，因此过滤了元组。

**方法一:使用列表理解**

在这种情况下，我们使用列表理解来检查元组的第 Kth 元素的每个元素是否以速记形式出现在列表中，并使用 In 运算符来测试包含性。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Filter Tuples by Kth element from List
# Using list comprehension

# initializing list
test_list = [("GFg", 5, 9), ("is", 4, 3), ("best", 10, 29)]

# printing original list
print("The original list is : " + str(test_list))

# initializing check_list
check_list = [4, 2, 8, 10]

# initializing K 
K = 1

# checking for presence on Kth element in list 
# one liner 
res = [sub for sub in test_list if sub[K] in check_list]

# printing result 
print("The filtered tuples : " + str(res))
```

**Output**

```py
The original list is : [('GFg', 5, 9), ('is', 4, 3), ('best', 10, 29)]
The filtered tuples : [('is', 4, 3), ('best', 10, 29)]

```

**方法 2:使用过滤器()+λ**

在这种情况下，lambda 函数检查元素是否存在，filter 执行过滤元组的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Filter Tuples by Kth element from List
# Using filter() + lambda

# initializing list
test_list = [("GFg", 5, 9), ("is", 4, 3), ("best", 10, 29)]

# printing original list
print("The original list is : " + str(test_list))

# initializing check_list
check_list = [4, 2, 8, 10]

# initializing K 
K = 1

# filter() perform filter, lambda func. checks for presence
# one liner 
res = list(filter(lambda sub: sub[K] in check_list, test_list))

# printing result 
print("The filtered tuples : " + str(res))
```

**Output**

```py
The original list is : [('GFg', 5, 9), ('is', 4, 3), ('best', 10, 29)]
The filtered tuples : [('is', 4, 3), ('best', 10, 29)]

```