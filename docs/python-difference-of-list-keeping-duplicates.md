# Python–列表保留副本的区别

> 原文:[https://www . geeksforgeeks . org/python-列表保留差异-重复/](https://www.geeksforgeeks.org/python-difference-of-list-keeping-duplicates/)

寻找列表之间差异的问题，即删除出现在一个列表中而不出现在另一个列表中的元素，之前已经讨论过。但是集合的使用忽略了重复，我们有时需要移除列表中出现的确切元素。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们以每次移除元素的形式提取元素，并打破循环一次移除一个元素。

```py
# Python3 code to demonstrate 
# Difference of List keeping duplicates
# using loop

# Initializing lists
test_list1 = [4, 5, 7, 4, 3]
test_list2 = [7, 3, 4]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Difference of List keeping duplicates
# using loop
for ele in test_list2:
    for sub in test_list1:
        if ele == sub:
            test_list1.remove(sub)
            break

# printing result 
print ("List after performing difference : " + str(test_list1))
```

**Output :**

```py
The original list 1 is : [4, 5, 7, 4, 3]
The original list 2 is : [7, 3, 4]
List after performing difference : [5, 4]

```