# Python–首 K 独特元素

> 原文:[https://www . geesforgeks . org/python-first-k-unique-elements/](https://www.geeksforgeeks.org/python-first-k-unique-elements/)

有时，在使用 Python Lists 时，我们可能会遇到一个问题，需要提取前 K 个唯一元素。这意味着，如果它们也出现在前 K 个元素中，我们需要提取重复。这实质上可以使前 K 个唯一元素的个数多于 K 个。这类问题可以在日常编程中应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [6，7，6，7]，K = 2
> **输出** : [6，7]
> 
> **输入** : test_list = [3，4，5，7]，K = 3
> **输出** : [3，4，5]

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们通过保留计数器和存储列表来比较以前的事件来执行获取元素的任务。

```
# Python3 code to demonstrate working of 
# First K unique elements
# Using loop

# initializing list
test_list = [6, 7, 6, 7, 8, 3, 9, 11]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# First K unique elements
# Using loop
store = []
res = []
cnt = 0
for ele in test_list:
    if ele not in store:
        cnt = cnt + 1
        store.append(ele)
    res.append(ele)
    if cnt >= K :
        break

# printing result 
print("The extracted elements : " + str(res)) 
```

**Output :**

```
The original list is : [6, 7, 6, 7, 8, 3, 9, 11]
The extracted elements : [6, 7, 6, 7, 8, 3]

```

**方法 2:使用`set() + filter() + lambda`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 set 和 filter()执行创建查找列表的任务，使用+ lambda 检查列表中的值。

```
# Python3 code to demonstrate working of 
# First K unique elements
# Using set() + filter() + lambda

# initializing list
test_list = [6, 7, 6, 7, 8, 3, 9, 11]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# First K unique elements
# Using set() + filter() + lambda
store = set(list({ele for ele in test_list})[:K])
res = list(filter(lambda ele: ele in store, test_list))

# printing result 
print("The extracted elements : " + str(res)) 
```

**Output :**

```
The original list is : [6, 7, 6, 7, 8, 3, 9, 11]
The extracted elements : [6, 7, 6, 7, 8, 3]

```