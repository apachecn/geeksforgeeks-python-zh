# Python–如果第 Kth 个元素不在列表中，则提取记录

> 原文:[https://www . geesforgeks . org/python-extract-records-if-kth-elements-不在列表中/](https://www.geeksforgeeks.org/python-extract-records-if-kth-elements-not-in-list/)

给定元组列表，任务是提取参数列表中不存在 Kth 索引元素的所有元组。

> **输入** : test_list = [(5，3)，(7，4)，(1，3)，(7，8)，(0，6)]，arg_list = [6，8，8]，K = 1
> 
> **输出** : [(5，3)，(7，4)，(1，3)]
> 
> **说明**:第一个索引中有 6 或 8 的元素全部被删除。
> 
> **输入** : test_list = [(5，3)，(7，4)]，arg_list = [3，3，3，3]，K = 1
> 
> **输出** : [(7，4)]
> 
> **说明** : (5，3)被删除，因为它在第一个索引处有 3。

**方法#1:使用 set() +循环**

这是完成这项任务的一种方式。在这种情况下，我们使用 set 来缩短参数列表，然后有效地检查是否有来自 arg 的任何元素的 Kth 索引。列出并相应追加。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract records if Kth elements not in List
# Using loop

# initializing list
test_list = [(5, 3), (7, 4), (1, 3), (7, 8), (0, 6)]

# printing original list
print("The original list : " + str(test_list))

# initializing arg. list
arg_list = [4, 8, 4]

# initializing K
K = 1

# Using set() to shorten arg list
temp = set(arg_list)

# loop to check for elements and append
res = []
for sub in test_list:
    if sub[K] not in arg_list:
        res.append(sub)

# printing result
print("Extracted elements : " + str(res))
```

**Output**

```py
The original list : [(5, 3), (7, 4), (1, 3), (7, 8), (0, 6)]
Extracted elements : [(5, 3), (1, 3), (0, 6)]

```

**方法 2:使用列表理解+集合()**

这是执行这项任务的另一种方式。在本文中，我们编译了使用 set()过滤重复项的任务和使用列表理解中的条件语句编译元素的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract records if Kth elements not in List
# Using list comprehension + set()

# initializing list
test_list = [(5, 3), (7, 4), (1, 3), (7, 8), (0, 6)]

# printing original list
print("The original list : " + str(test_list))

# initializing arg. list
arg_list = [4, 8, 4]

# initializing K
K = 1

# Compiling set() and conditionals into single comprehension
res = [(key, val) for key, val in test_list if val not in set(arg_list)]

# printing result
print("Extracted elements : " + str(res))
```

**Output**

```py
The original list : [(5, 3), (7, 4), (1, 3), (7, 8), (0, 6)]
Extracted elements : [(5, 3), (1, 3), (0, 6)]

```