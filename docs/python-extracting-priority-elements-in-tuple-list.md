# Python–提取元组列表中的优先级元素

> 原文:[https://www . geesforgeks . org/python-提取-优先级-元组列表中的元素/](https://www.geeksforgeeks.org/python-extracting-priority-elements-in-tuple-list/)

有时，在使用 Python Records 时，我们可能会遇到一个问题，即我们需要从记录中提取所有优先级元素，这些元素通常作为二进制元素元组之一出现。这种问题在网络开发和游戏领域可能会有应用。让我们讨论执行这项任务的某些方法。

> **输入** :
> 测试 _ 列表= [(7，1)，(3，2)，(4，6)]
> 优先 _ 列表= [1，3，4]
> **输出**:【1，3，4】
> 
> **输入** :
> 测试 _ 列表= [(7，3)，(3，4)，(1，6)]
> 优先 _ 列表= [1，3，4]
> **输出**:【3，4，1】

**方法#1:使用循环**
这是解决这个问题的蛮力方法。在这种情况下，我们迭代优先级列表的每个元素并检查单个元组，过滤掉匹配的元素并追加到列表中。

```
# Python3 code to demonstrate working of 
# Extracting Priority Elements in Tuple List
# loop

# initializing list
test_list = [(5, 1), (3, 4), (9, 7), (10, 6)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Priority list 
prior_list = [6, 4, 7, 1]

# Extracting Priority Elements in Tuple List
# loop
res = []
for sub in test_list:
    for val in prior_list:
        if val in sub:
            res.append(val)

# printing result 
print("The extracted elements are : " + str(res)) 
```

**Output :**

```
The original list is : [(5, 1), (3, 4), (9, 7), (10, 6)]
The extracted elements are : [1, 4, 7, 6]

```

**方法 2:使用列表理解+ `index()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 index()和优先级比较来执行从元组中检查所需元素的任务。

```
# Python3 code to demonstrate working of 
# Extracting Priority Elements in Tuple List
# Using List comprehension + <code>index()

# initializing list
test_list = [(7, 1), (6, 4), (4, 7), (1, 6)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Priority list 
prior_list = [6, 4, 7, 1]

# Extracting Priority Elements in Tuple List
# Using List comprehension + <code>index()
res = [sub[0] if prior_list.index(sub[0]) < prior_list.index(sub[1])
              else sub[1] for sub in test_list]

# printing result 
print("The extracted elements are : " + str(res)) 
```

**Output :**

```
The original list is : [(7, 1), (6, 4), (4, 7), (1, 6)]
The extracted elements are : [7, 6, 4, 6]

```