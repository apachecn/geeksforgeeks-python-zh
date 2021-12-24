# Python |将字符串列表转换为连接的单个元素

> 原文:[https://www . geesforgeks . org/python-convert-string-list-to-joined-single-element/](https://www.geeksforgeeks.org/python-convert-string-list-to-joined-single-element/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们需要通过使用 delim 组合来执行将 String 列表的每个元素连接到 list 中的单个元素的任务。这种应用可以出现在 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是执行这个任务的方法之一。在本文中，我们使用循环迭代字符串的字符串列表，并根据 delim 执行连接操作。

```
# Python3 code to demonstrate working of 
# Convert String list to Joined Single element
# Using loop

# initializing list
test_list = ['gfg', 'is', 'best']

# printing original list
print("The original list is : " + str(test_list))

# initializing delim 
delim = "-"

# Convert String list to Joined Single element
# Using loop
res = ''  
for idx in range(len(test_list)-1):
    res = res + test_list[idx] + delim
if len(test_list) > 0:
        res = res + test_list[-1]
res = [res]

# printing result 
print("String after performing join : " + str(res)) 
```

**Output :**

```
The original list is : ['gfg', 'is', 'best']
String after performing join : ['gfg-is-best']

```