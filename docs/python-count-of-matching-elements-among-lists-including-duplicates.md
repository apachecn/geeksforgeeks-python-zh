# Python–列表中匹配元素的数量(包括重复项)

> 原文:[https://www . geesforgeks . org/python-列表中匹配元素的计数-包括重复项/](https://www.geeksforgeeks.org/python-count-of-matching-elements-among-lists-including-duplicates/)

给定两个列表，计算两个列表中相似的所有元素，包括重复的。

> **输入** : test_list1 = [3，5，6，7，2，3，5]，test_list2 = [5，5，3，9，8，5]
> **输出** : 4
> **解释** : 3 重复 2 次，5 两次，共计 4。
> 
> **输入** : test_list1 = [3，5，6]，test_list2 = [5，3，9]
> **输出** : 2
> **解释** : 3 重复 1 次，5 重复 1 次，共计 2。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们迭代其他列表的每个元素，同时迭代一个列表，并增加计数器。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Count of matching elements among lists [ Including duplicates ]
# Using loop

# initializing lists
test_list1 = [3, 5, 6, 7, 2, 3]
test_list2 = [5, 5, 3, 9, 8]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using loop to iterate each element
res = 0
for ele in test_list1:
    if ele in test_list2:
        res += 1

# printing result 
print("All matching elements : " + str(res))
```

**Output**

```py
The original list 1 : [3, 5, 6, 7, 2, 3]
The original list 2 : [5, 5, 3, 9, 8]
All matching elements : 3

```

**方法 2:使用 sum() +生成器表达式**

上述方法的结合被用来解决这个问题。在本文中，我们使用 sum()对元素进行计数，生成器表达式执行迭代任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Count of matching elements among lists [ Including duplicates ]
# Using sum() + generator expression

# initializing lists
test_list1 = [3, 5, 6, 7, 2, 3]
test_list2 = [5, 5, 3, 9, 8]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using sum to count occurrences
res = sum(ele in test_list1 for ele in test_list2)

# printing result 
print("All matching elements : " + str(res))
```

**Output**

```py
The original list 1 : [3, 5, 6, 7, 2, 3]
The original list 2 : [5, 5, 3, 9, 8]
All matching elements : 3

```