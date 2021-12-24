# Python–从列表中提取元素，K

成功

> 原文:[https://www . geesforgeks . org/python-extract-element-from-list-succeed-by-k/](https://www.geeksforgeeks.org/python-extract-element-from-list-succeeded-by-k/)

给定一个列表，提取具有 K 的元素作为下一个元素。

> **输入** : test_list = [2，3，5，7，8，5，3，5]，K = 3
> **输出** : [2，5]
> **解释**:3 之前的元素为 2，5。
> 
> **输入**:test _ list =【2，3，5，7，8，5，3，8】，K = 8
> **输出**:【7，3】
> **解释**:8 之前的元素是 7，3。

**方法#1:使用循环**

在这种情况下，我们迭代列表并寻找每个 K，并提取它前面的元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract elements succeeded by K
# Using loop

# initializing list
test_list = [2, 3, 5, 7, 8, 5, 3, 5]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# Using loop to extract elements succeeded by K
res = []
for idx in range(len(test_list) - 1):

    # checking for succession
    if test_list[idx + 1] == K:
        res.append(test_list[idx])

# printing result
print("Extracted elements list : " + str(res))
```

**Output**

```
The original list is : [2, 3, 5, 7, 8, 5, 3, 5]
Extracted elements list : [3, 8, 3]

```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

解决这个问题的另一种方法，在这里，我们使用列表理解作为速记来解决获取元素的问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract elements succeeded by K
# Using list comprehension

# initializing list
test_list = [2, 3, 5, 7, 8, 5, 3, 5]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# List comprehension used as shorthand
res = [test_list[idx]
       for idx in range(len(test_list) - 1) if test_list[idx + 1] == K]

# printing result
print("Extracted elements list : " + str(res))
```

**Output**

```
The original list is : [2, 3, 5, 7, 8, 5, 3, 5]
Extracted elements list : [3, 8, 3]

```