# Python–检查列表中的前一个元素是否更小

> 原文:[https://www . geesforgeks . org/python-check-if-previous-element-is-small-in-list/](https://www.geeksforgeeks.org/python-check-if-previous-element-is-smaller-in-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要检查每个元素的前一个元素是否更小。这类问题在数据预处理领域有其用途。让我们讨论一下可以执行这项任务的某些问题。

> **输入**:test _ list =【1，3，5，6，8】
> **输出**:【真，真，真，真】
> **输入**:test _ list =【3，1】
> **输出**:【假】

**方法#1:使用循环**
这是执行该任务的方法之一。在本文中，我们使用循环中的暴力来执行检查元素的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Check if previous element is smaller in List
# Using loop

# initializing list
test_list = [6, 3, 7, 3, 6, 7, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

# Check if previous element is smaller in List
# Using loop
res = []
for idx in range(1, len(test_list)):
    if test_list[idx - 1] < test_list[idx]:
        res.append(True)
    else:
        res.append(False)

# printing result
print("List after filtering : " + str(res))
```

**Output : **

```
The original list is : [6, 3, 7, 3, 6, 7, 8, 3]
List after filtering : [False, True, False, True, True, True, False]
```

**方法#2:使用 zip() +列表理解**
这是解决这个问题的一个线性方法。在这种情况下，我们首先压缩列表及其下一个元素列表，然后检查结果的比较。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Check if previous element is smaller in List
# Using zip() + list comprehension

# initializing list
test_list = [6, 3, 7, 3, 6, 7, 8, 3]

# printing original list
print("The original list is : " + str(test_list))

# Check if previous element is smaller in List
# Using zip() + list comprehension
res = [int(sub1) < int(sub2) for sub1, sub2 in zip(test_list, test_list[1:])]

# printing result
print("List after filtering : " + str(res))
```

**Output : **

```
The original list is : [6, 3, 7, 3, 6, 7, 8, 3]
List after filtering : [False, True, False, True, True, True, False]
```