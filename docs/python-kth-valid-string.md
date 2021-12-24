# Python–第 Kth 个有效字符串

> 原文:[https://www.geeksforgeeks.org/python-kth-valid-string/](https://www.geeksforgeeks.org/python-kth-valid-string/)

有时在处理数据科学时，我们需要处理大量数据，因此我们可能需要人手不足来执行某些任务。我们在预处理阶段处理空值，因此有时需要检查 Kth 有效元素。让我们讨论一下找到第 k 个非空字符串的某些方法。

**方法#1:使用`next()` +列表理解**
下一个函数返回迭代器，因此使用检查最后一个无值的列表理解来处理传统的列表理解和逻辑部分更有效。

```
# Python3 code to demonstrate
# Kth Valid String
# using next() + list comprehension

# initializing list
test_list = ["", "", "Akshat", "Nikhil"]

# printing original list 
print("The original list : " + str(test_list))

# initializing K 
K = 2

# using next() + list comprehension
# Kth Valid String
test_list = iter(test_list)
for idx in range(0, K):
    res = next(sub for sub in test_list if sub)

# printing result
print("The Kth non empty string is : " + str(res))
```

**Output :**

```
The original list : ['', '', 'Akshat', 'Nikhil']
The Kth non empty string is : Nikhil

```