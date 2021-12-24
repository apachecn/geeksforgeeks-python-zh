# Python–列表中的元素长度

> 原文:[https://www . geesforgeks . org/python-elements-length-in-list/](https://www.geeksforgeeks.org/python-elements-lengths-in-list/)

有时，在使用 Python 列表时，可能会遇到这样的问题，即我们需要计算列表中元素的大小。这是因为列表可以允许不同的元素类型成为其成员。这种问题可以应用于许多领域，例如日常编程和 web 开发。让我们讨论一下执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们迭代每个循环元素，并使用元素计数器找到它的大小。

```
# Python3 code to demonstrate working of 
# Elements Lengths in List
# Using loop

# initializing list
test_list = ['GFG', (4, 5, 6), 17, [5, 6, 7, 8], 'Best']

# printing original list
print("The original list is : " + str(test_list))

# Elements Lengths in List
# Using loop
res = []
for ele in test_list:
    count = 0
    if type(ele) == int:
        res.append(1)
    else :
        for sub in ele:
            count = count + 1
        res.append(count)

# printing result 
print("The element sizes in order are : " + str(res)) 
```

**Output :**

```
The original list is : ['GFG', (4, 5, 6), 17, [5, 6, 7, 8], 'Best']
The element sizes in order are : [3, 3, 1, 4, 4]

```