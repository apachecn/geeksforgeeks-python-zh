# Python–K 元素列出相似的索引值

> 原文:[https://www . geesforgeks . org/python-elements-with-k-list-相似-index-value/](https://www.geeksforgeeks.org/python-elements-with-k-lists-similar-index-value/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要在特定的索引中获取 K 列表中相似的元素。这可以应用于许多领域，如日常和其他领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip()` +循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们迭代压缩列表中的循环，并与特定索引中的元素进行相似性比较。

```
# Python3 code to demonstrate 
# Elements with K lists similar index value
# using zip() + loop

# Initializing lists
test_list1 = [1, 3, 5, 7]
test_list2 = [1, 4, 8, 9]
test_list3 = [3, 7, 5, 10]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))
print("The original list 3 is : " + str(test_list3))

# Initializing K 
K = 2

# Elements with K lists similar index value
# using zip() + loop
res = []
for a, b, c in zip(test_list1, test_list2, test_list3):
    if a == b or b == c or c == a:
        if a == b:
            res.append(a)
        elif b == c:
            res.append(b)
        elif c == a:
            res.append(c)

# printing result 
print ("The list after checking on 2 lists : " + str(res))
```

**Output :**

```
The original list 1 is : [1, 3, 5, 7]
The original list 2 is : [1, 4, 8, 9]
The original list 3 is : [3, 7, 5, 10]
The list after checking on 2 lists : [1, 5]

```