# Python–过滤连续元素元组

> 原文:[https://www . geesforgeks . org/python-filter-continuous-elements-元组/](https://www.geeksforgeeks.org/python-filter-consecutive-elements-tuples/)

给定元组列表，过滤由连续元素组成的元组，即 diff 为 1。

> **输入** : test_list = [(3，4，5，6)，(5，6，7，2)，(1，2，4)，(6，4，6，3)]
> **输出** : [(3，4，5，6)]
> **解释**:只有 1 个元组符合条件。
> 
> **输入** : test_list = [(3，4，5，6)，(5，6，7，2)，(1，2，3)，(6，4，6，3)]
> **输出** : [(3，4，5，6)，(1，2，3)]
> **解释**:只有 2 个元组符合条件。

**方法#1:使用循环**

在这种情况下，对于每个元组，我们调用连续元素实用程序，如果元组是连续的，则返回真。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter consecutive elements Tuples
# Using loop

# hlpr_func 
def consec_check(tup):
    for idx in range(len(tup) - 1):

        # returns false if any element is not consec.
        if tup[idx + 1] != tup[idx] + 1:
            return False 

    return True 

# initializing list
test_list = [(3, 4, 5, 6), (5, 6, 7, 2), (1, 2, 3), (6, 4, 6, 3)]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:

    # calls fnc to check consec.
    if consec_check(sub):
        res.append(sub)

# printing result 
print("The filtered tuples : " + str(res))
```

**Output**

```
The original list is : [(3, 4, 5, 6), (5, 6, 7, 2), (1, 2, 3), (6, 4, 6, 3)]
The filtered tuples : [(3, 4, 5, 6), (1, 2, 3)]

```

**方法 2:使用列表理解**

在这种情况下，我们执行与上面类似的功能，只是使用列表理解进行单行速记。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter consecutive elements Tuples
# Using list comprehension

# hlpr_func 
def consec_check(tup):
    for idx in range(len(tup) - 1):

        # returns false if any element is not consec.
        if tup[idx + 1] != tup[idx] + 1:
            return False 

    return True 

# initializing list
test_list = [(3, 4, 5, 6), (5, 6, 7, 2), (1, 2, 3), (6, 4, 6, 3)]

# printing original list
print("The original list is : " + str(test_list))

# one-liner to solve problem, using list comprehension
res = [sub for sub in test_list if consec_check(sub)]

# printing result 
print("The filtered tuples : " + str(res))
```

**Output**

```
The original list is : [(3, 4, 5, 6), (5, 6, 7, 2), (1, 2, 3), (6, 4, 6, 3)]
The filtered tuples : [(3, 4, 5, 6), (1, 2, 3)]

```