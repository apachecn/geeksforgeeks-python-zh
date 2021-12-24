# Python–从 jth 列值中提取第个列值

> 原文:[https://www . geesforgeks . org/python-extract-ith-column-values-from-jth-column-values/](https://www.geeksforgeeks.org/python-extract-ith-column-values-from-jth-column-values/)

有时，在使用 Python Matrix 时，我们可能会遇到一个问题，即需要通过比较 jth 列的值来提取第 I 列的值。这种问题可能发生在学校编程或网络开发等领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [[4，5，6]，[2，5，7]，[9，8，2]，[10，2，6]]，search_list = [4，9]，search_idx = 0，ext_idx = 2
> **输出** : [6，2]
> 
> **输入** : test_list = [[4，5，6]，[2，5，7]，[9，8，2]，[10，2，6]]，search_list = [2，6]，search_idx = 2，ext_idx = 0
> **输出** : [4，9，10]

**方法#1:使用循环**
这是解决这个问题的蛮方法。在这种情况下，我们循环遍历每一行，并将 jth 列与列表元素进行比较，如果列表元素存在，则提取 ith 元素。

```py
# Python3 code to demonstrate working of 
# Extract ith column values from jth column values
# Using loop

# initializing list
test_list = [[4, 5, 6], [2, 5, 7], [9, 8, 2], [10, 2, 6]]

# printing original list
print("The original list is : " + str(test_list))

# initializing list 
search_list = [5, 2]

# initializing search index 
search_idx = 1

# initializing extract index
ext_idx = 2

# Extract ith column values from jth column values
# Using loop
res = []
for sub in test_list:
    if sub[search_idx] in search_list:
        res.append(sub[ext_idx])

# printing result 
print("The extracted elements : " + str(res)) 
```

**Output :**

```py
The original list is : [[4, 5, 6], [2, 5, 7], [9, 8, 2], [10, 2, 6]]
The extracted elements : [6, 7, 6]

```

**方法 2:使用`set() + list comprehension`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们以与上述方法类似的方式执行提取元素的任务，只是使用速记。此外，对于初始数据搜索缩减，搜索列表被转换为 set()，以移除重复的。

```py
# Python3 code to demonstrate working of 
# Extract ith column values from jth column values
# Using set() + list comprehension

# initializing list
test_list = [[4, 5, 6], [2, 5, 7], [9, 8, 2], [10, 2, 6]]

# printing original list
print("The original list is : " + str(test_list))

# initializing list 
search_list = [5, 2]

# initializing search index 
search_idx = 1

# initializing extract index
ext_idx = 2

# Extract ith column values from jth column values
# Using set() + list comprehension
temp = set(search_list)
res = [sub[ext_idx] for sub in test_list if sub[search_idx] in search_list]

# printing result 
print("The extracted elements : " + str(res)) 
```

**Output :**

```py
The original list is : [[4, 5, 6], [2, 5, 7], [9, 8, 2], [10, 2, 6]]
The extracted elements : [6, 7, 6]

```