# Python–连续相同元素计数

> 原文:[https://www . geeksforgeeks . org/python-连续-相同-元素-计数/](https://www.geeksforgeeks.org/python-consecutive-identical-elements-count/)

给定元素列表，获取所有与下一个元素具有相同元素的元素。

> **输入** : test_list = [4，5，5，5，5，6，6，7，8，2，2，10]
> **输出** : 3
> **解释** : 5，6，2 有相同的元素作为它们的下一个元素。
> 
> **输入** : test_list = [4，5，5，5，5，6，6，7，8，2，3，10]
> **输出** : 2
> **解释** : 5 和 6 有相同的元素作为它们的下一个元素。

**方法#1:使用循环+ set()**

在这种情况下，我们迭代并检查下一个元素，如果等于当前，我们在结果列表中添加，然后它被转换为集合以获得不同的元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Consecutive identical elements count
# Using loop + set()

# initializing list
test_list = [4, 5, 5, 5, 5, 6, 6, 7, 8, 2, 2, 10]

# printing original list
print("The original list is : " + str(test_list))

res = []
for idx in range(0, len(test_list) - 1):

    # getting Consecutive elements 
    if test_list[idx] == test_list[idx + 1]:
        res.append(test_list[idx])

# getting count of unique elements        
res = len(list(set(res)))

# printing result 
print("Consecutive identical elements count : " + str(res))
```

**Output**

```
The original list is : [4, 5, 5, 5, 5, 6, 6, 7, 8, 2, 2, 10]
Consecutive identical elements count : 3

```

**方法 2:使用列表理解+ set() + len()**

这种方法与上述方法相似，不同的是它解决这个问题的方法较短。len()和 set()用于获取唯一元素计数的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Consecutive identical elements count
# Using list comprehension + set() + len()

# initializing list
test_list = [4, 5, 5, 5, 5, 6, 6, 7, 8, 2, 2, 10]

# printing original list
print("The original list is : " + str(test_list))

# getting Consecutive elements
res = [test_list[idx] for idx in range(
    0, len(test_list) - 1) if test_list[idx] == test_list[idx + 1]]

# getting count of unique elements
res = len(list(set(res)))

# printing result
print("Consecutive identical elements count : " + str(res))
```

**Output**

```
The original list is : [4, 5, 5, 5, 5, 6, 6, 7, 8, 2, 2, 10]
Consecutive identical elements count : 3

```