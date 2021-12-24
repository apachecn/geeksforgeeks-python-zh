# Python |真数第一次出现

> 原文:[https://www . geeksforgeeks . org/python-首次出现真数/](https://www.geeksforgeeks.org/python-first-occurrence-of-true-number/)

很多时候，我们需要找到第一个出现的非零数字来开始处理。这主要是机器学习领域的用例，我们需要处理除*无*或 *0 值*之外的数据。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`next() + enumerate()`**
下一个函数可以用来遍历列表，并与其一起枚举，检查列表中的数字是否为非零元素，并返回真值(即非零值)之前的 0 数。

```py
# Python3 code to demonstrate 
# finding first True value 
# using next() and enumerate()

# initializing list 
test_list = [ 0, 0, 5, 6, 0]

# printing original list
print ("The original list is : " + str(test_list))

# finding first True value
# using next() and enumerate()
res = next((i for i, j in enumerate(test_list) if j), None)

# printing result
print ("The values till first True value : " + str(res))
```

**Output:**

```py
The original list is : [0, 0, 5, 6, 0]
The values till first True value : 2

```

**方法 2:使用`filter() + lamda + index()`**
使用上述功能的组合，可以轻松执行该特定任务。`filter` 函数可用于筛选出由 lambda 函数处理的真值，索引函数返回第一次出现的真值。

```py
# Python3 code to demonstrate 
# finding first True value 
# using filter() + lamda + index()

# initializing list 
test_list = [ 0, 0, 5, 6, 0]

# printing original list
print ("The original list is : " + str(test_list))

# finding first True value
# using filter() + lamda + index()
res = test_list.index(next(filter(lambda i: i != 0, test_list)))

# printing result
print ("The values till first True value : " + str(res))
```

**Output:**

```py
The original list is : [0, 0, 5, 6, 0]
The values till first True value : 2

```