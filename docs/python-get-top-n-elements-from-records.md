# Python |从记录中获取前 N 个元素

> 原文:[https://www . geesforgeks . org/python-get-top-n-elements-from-records/](https://www.geeksforgeeks.org/python-get-top-n-elements-from-records/)

有时，在处理数据时，我们会遇到一个问题，我们有记录，我们需要从中找到最高的 N 分。这种应用在 web 开发领域非常流行。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`sorted()`+λ**
上述功能的组合可用于执行该特定任务。在这种情况下，我们只使用反向标志为真的排序函数，并使用列表切片打印前 N 个元素。

```
# Python3 code to demonstrate working of
# Get Top N elements from Records
# Using sorted() + lambda

# Initializing list 
test_list = [('Manjeet', 10), ('Akshat', 4), ('Akash', 2), ('Nikhil', 8)]

# Initializing N 
N = 2

# printing original list
print("The original list is : " + str(test_list))

# Get Top N elements from Records
# Using sorted() + lambda
res = sorted(test_list, key = lambda x: x[1], reverse = True)[:N]

# printing result
print("The top N records are : " + str(res))
```

**Output :**

```
The original list is : [('Manjeet', 10), ('Akshat', 4), ('Akash', 2), ('Nikhil', 8)]
The top N records are : [('Manjeet', 10), ('Nikhil', 8)]

```