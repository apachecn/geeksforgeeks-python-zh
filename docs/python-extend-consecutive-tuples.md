# Python–扩展连续元组

> 原文:[https://www . geesforgeks . org/python-extend-continuous-元组/](https://www.geeksforgeeks.org/python-extend-consecutive-tuples/)

给定元组列表，连接连续元组。

> **输入** : test_list = [(3，5，6，7)，(3，2，4，3)，(9，4)，(2，3，2)]
> **输出** : [(3，5，6，7，3，2，4，3)，(3，2，4，3，9，4)，(9，4，2，3，2)]
> **解释**:元素与其连续元组连接。
> 
> **输入** : test_list = [(3，5，6，7)，(3，2，4，3)]
> **输出** : [(3，5，6，7，3，2，4，3)]
> **解释**:元素与其连续元组连接。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们通过访问内部循环来执行连接连续的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extend consecutive tuples
# Using loop

# initializing list
test_list = [(3, 5, 6, 7), (3, 2, 4, 3), (9, 4), (2, 3, 2), (3, ), (3, 6)]

# printing original list
print("The original list is : " + str(test_list))

res = []
for idx in range(len(test_list) - 1):

    # joining tuples
    res.append(test_list[idx] + test_list[idx + 1])

# printing results
print("Joined tuples : " + str(res))
```

**Output**

```
The original list is : [(3, 5, 6, 7), (3, 2, 4, 3), (9, 4), (2, 3, 2), (3, ), (3, 6)]
Joined tuples : [(3, 5, 6, 7, 3, 2, 4, 3), (3, 2, 4, 3, 9, 4), (9, 4, 2, 3, 2), (2, 3, 2, 3), (3, 3, 6)]

```

**方法二:使用 zip() +列表理解**

在这种情况下，我们使用 zip()和切片构建连续列表，然后相应地形成对。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extend consecutive tuples
# Using zip() + list comprehension

# initializing list
test_list = [(3, 5, 6, 7), (3, 2, 4, 3), (9, 4), (2, 3, 2), (3, ), (3, 6)]

# printing original list
print("The original list is : " + str(test_list))

# zip to combine consecutive elements 
res = [a + b for a, b in zip(test_list, test_list[1:])]

# printing results
print("Joined tuples : " + str(res))
```

**Output**

```
The original list is : [(3, 5, 6, 7), (3, 2, 4, 3), (9, 4), (2, 3, 2), (3, ), (3, 6)]
Joined tuples : [(3, 5, 6, 7, 3, 2, 4, 3), (3, 2, 4, 3, 9, 4), (9, 4, 2, 3, 2), (2, 3, 2, 3), (3, 3, 6)]

```