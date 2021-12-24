# Python–按照给定顺序连接字符串

> 原文:[https://www . geesforgeks . org/python-按给定顺序连接字符串/](https://www.geeksforgeeks.org/python-concatenate-strings-in-the-given-order/)

给定字符串列表和顺序列表，以特定顺序执行字符串连接。

> **输入**:test _ list =[“best”、“Gfg”、“for”、“is”]，sort_order = [1，3，0，2]
> **输出**:Ggfgisbestfor
> **解释**:按指数顺序组合。
> 
> **输入**:test _ list =[“best”、“Gfg”]，sort_order = [1，0]
> **输出** : Gfgbest
> **解释**:按指数顺序组合。

**方法#1:使用循环**

在这种情况下，我们迭代循环中的顺序元素，并以相似的顺序执行相似索引的字符串的串联。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Concatenate Strings in Order
# Using loop

# initializing list
test_list = ["best", "Gfg", "for", "is", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing join order
sort_order = [1, 3, 0, 2, 4]

res = ''
for order in sort_order:

    # concatenating by order
    res += test_list[order]

# printing result
print("Ordered concatenation : " + str(res))
```

**Output**

```
The original list is : ['best', 'Gfg', 'for', 'is', 'geeks']
Ordered concatenation : Gfgisbestforgeeks
```

**方法 2:使用 join() +列表理解**

在本文中，我们使用 join()执行连接任务，列表理解用于顺序的迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Concatenate Strings in Order
# Using join() + list comprehension

# initializing list
test_list = ["best", "Gfg", "for", "is", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing join order
sort_order = [1, 3, 0, 2, 4]

# join() performs concatenation
res = ''.join([test_list[order] for order in sort_order])

# printing result
print("Ordered concatenation : " + str(res))
```

**Output**

```
The original list is : ['best', 'Gfg', 'for', 'is', 'geeks']
Ordered concatenation : Gfgisbestforgeeks
```