# Python–替代列表元素

> 原文:[https://www . geesforgeks . org/python-alternate-list-elements/](https://www.geeksforgeeks.org/python-alternate-list-elements/)

给定两个列表，以之字形方式打印元素，即打印列表的相似索引，然后继续下一步。

> **输入** : test_list1 = [5，3，1]，test_list2 = [6，4，2]
> **输出** : [5，6，3，4，1，2，4]
> **解释**:第 0 个索引中的 5 和 6 先打印，第 1 个索引中的 3 和 4 再打印，以此类推。
> 
> **输入** : test_list1 = [5，3，1，9]，test_list2 = [6，4，2，10]
> **输出** : [5，6，3，4，1，2，4，9，10]
> **解释**:第 0 个索引中的 5 和 6 先打印，第 1 个索引中的 3 和 4 再打印，以此类推。

**方法#1:使用循环**

这是执行这项任务的方法之一。在这里，我们简单地执行迭代，并在结果列表中一个接一个地添加相似的索引元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Alternate List elements
# Using loop

# initializing lists
test_list1 = [5, 3, 1, 4, 7]
test_list2 = [6, 4, 2, 5, 1]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Using loop to print elements in criss cross manner
res = []
for idx in range(0, len(test_list1)):
    res.append(test_list1[idx])
    res.append(test_list2[idx])

# printing result
print("The zig-zag printing of elements : " + str(res))
```

**Output**

```
The original list 1 : [5, 3, 1, 4, 7]
The original list 2 : [6, 4, 2, 5, 1]
The zig-zag printing of elements : [5, 6, 3, 4, 1, 2, 4, 5, 7, 1]

```

**方法 2:使用 zip() + loop**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 zip()将每个元素与相似的索引配对，然后使用循环将每个元素馈送到结果列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Alternate List elements
# Using  zip() + loop

# initializing lists
test_list1 = [5, 3, 1, 4, 7]
test_list2 = [6, 4, 2, 5, 1]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Using zip() to perform pairing and loop to 
# get elements into result list
res = []
for ele1, ele2 in zip(test_list1, test_list2):
    res.append(ele1)
    res.append(ele2)

# printing result 
print("The zig-zag printing of elements : " + str(res))
```

**Output**

```
The original list 1 : [5, 3, 1, 4, 7]
The original list 2 : [6, 4, 2, 5, 1]
The zig-zag printing of elements : [5, 6, 3, 4, 1, 2, 4, 5, 7, 1]

```