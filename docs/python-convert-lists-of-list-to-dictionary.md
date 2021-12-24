# Python–将列表转换为字典

> 原文:[https://www . geesforgeks . org/python-convert-list-of-list-to-dictionary/](https://www.geeksforgeeks.org/python-convert-lists-of-list-to-dictionary/)

有时，在处理 Python 记录时，我们可能会遇到这样的问题，即我们有列表形式的数据，我们需要将某些元素分配为键，某些元素分配为值以形成字典。这种类型的应用可以出现在数据域中。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是我们执行这个任务的野蛮方式。在这种情况下，我们根据所需的切片迭代形成键值对的列表。

```
# Python3 code to demonstrate working of 
# Convert Lists of List to Dictionary
# Using loop

# initializing list
test_list = [['a', 'b', 1, 2], ['c', 'd', 3, 4], ['e', 'f', 5, 6]]

# printing original list
print("The original list is : " + str(test_list))

# Convert Lists of List to Dictionary
# Using loop
res = dict()
for sub in test_list:
    res[tuple(sub[:2])] = tuple(sub[2:])

# printing result 
print("The mapped Dictionary : " + str(res)) 
```

**Output :**

> 原始列表为:[['a '，' b '，1，2]，['c '，' d '，3，4]，['e '，' f '，5，6]]
> 映射字典:{('c '，' d'): (3，4)，(' e '，' f ':(5，6)，(' a '，' b ':(1，2)}