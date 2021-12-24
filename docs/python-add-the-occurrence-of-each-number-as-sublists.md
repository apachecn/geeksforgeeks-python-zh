# Python |添加每个数字的出现作为子列表

> 原文:[https://www . geesforgeks . org/python-将每个数字的出现添加为子列表/](https://www.geeksforgeeks.org/python-add-the-occurrence-of-each-number-as-sublists/)

给定一个数字列表，任务是统计每个元素的出现次数，并将其添加为子列表。

**示例:**

```
Input: l1 = [3, 5, 7, 2, 3, 5, 9.1]
Output: [[3, 2], [5, 2], [7, 1], [2, 1], [9.1, 1]]

Input: l1 = [1, 1, 2, 2, 3, 1]
Output: [[1, 3], [2, 2], [3, 1]]

```

**注意:**格式输出 2d 列表为[['item1 '，' count1']，['item2 '，' count2']，…，['itemN '，' countN']]。

**代码#1:** 使用 count()方法

```
# Python program to add the occurrence
# of each number as sublists
def count_occur(list1, **kwargs):

    # iterate over list item
    for i in list1:
        row =[]
        ct = 0

        # count function will count occurrence
        ct = list1.count(i)
        row.append(i)
        row.append(ct)
        # append 1d list items to 2d list
        list2.append(row)

    # below code is to eliminate 
    # repetitive list items
    for j in list2:
        if j not in unq_l2:
            unq_l2.append(j)

    return unq_l2

# Driver Code
l1 = [3, 5, 7, 2, 3, 5, 9.1]
list2 = []
unq_l2 = []
print(count_occur(l1))
```

**Output:**

```
[[3, 2], [5, 2], [7, 1], [2, 1], [9.1, 1]]

```

**代码#2:** 使用循环法

```
def count_occur(list1):

    for i in range(0, len(l1)):
        a = 0
        row =[]
        if i not in l:
            for j in range(0, len(l1)):

                # matching items from both lists
                if l1[i]== l1[j]:

                    # on match counter increments by 1
                    a = a + 1

            row.append(l1[i])
            row.append(a)

            # append function will append 
            # 1d list items to 2d list
            l.append(row)

    # below code is to eliminate
    # repetitive list items    
    for j in l:
        if j not in unq_l:
            unq_l.append(j)

    return unq_l

# Driver code        
l1 =[3, 5, 7, 2, 3, 5, 9.1]
l =[]
unq_l =[]

print(count_occur(l1)) 
```

**Output:**

```
[[3, 2], [5, 2], [7, 1], [2, 1], [9.1, 1]]

```

**代码#3:** 使用计数器()方法

```
# Python program to add the occurrence
# of each number as sublists using counter() method

from collections import Counter
def count_occurence(l):
    c = Counter(l)
    l1 = []
    for k,v in c.items():
        l1.append([k,v])
    return l1

# Driver code     
l = [3, 5, 7, 2, 3, 5, 9.1]
print(count_occurence(l))
```

**Output:**

```
[[2, 1], [3, 2], [9.1, 1], [5, 2], [7, 1]]

```