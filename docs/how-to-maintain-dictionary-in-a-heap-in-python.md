# Python 中如何在堆里维护字典？

> 原文:[https://www . geesforgeks . org/如何在 python 堆中维护字典/](https://www.geeksforgeeks.org/how-to-maintain-dictionary-in-a-heap-in-python/)

**先决条件:**

*   [二进制堆数据结构](https://www.geeksforgeeks.org/binary-heap/)
*   [Python 中的 heapq 模块](https://www.geeksforgeeks.org/heap-queue-or-heapq-in-python/)
*   [Python 中的字典](https://www.geeksforgeeks.org/python-dictionary/)。

字典可以根据键或值在堆中维护。需要维护的约定如下:

*   索引“ **i** 处的键值对被认为是索引 **2k+1** 和 **2k+2** 处键值对的父项。
*   对于最小堆，父键/值必须小于其子键/值。
*   对于最大堆，父项/值必须大于其子项。

**示例:**

> **普通字典:{11:2，0:4，5:9，22:7}**
> 
> **基于字典关键字的堆:** {0: 4，1: 1，5: 9，22: 7，11: 2}
> 
> **基于字典值的堆:** {11: 2，0: 4，5: 9，22: 7}

本文展示了如何使用 heapq 模块在最小堆中维护字典。

## 普通字典堆

在 heapq 模块的帮助下，可以在堆结构中维护以整数/字符串为关键字的普通字典。但是这个模块期望一个列表被传递。这里使用的方法是:

1.  将键值对转换为元组列表。
2.  将元组列表传递给 **heapify()** 函数。
3.  再次将结果列表转换为字典。

**注意:**元组上的 heapify()会考虑该进程元组中的第一个元素。因此，默认情况下，字典仅基于关键字在堆中维护。

**示例 1:基于整数的键**

考虑一个字典，其中键是正整数，值是它们的平方。现在，这应该保持在一堆。

## 蟒蛇 3

```py
# import modules
import heapq as hq

# dictionary to be heapified
dict_1 = {11: 121, 2: 4, 5: 25, 3: 9}

# convert dictionary to list of tuples
di = list(dict_1.items())

print("dictionary into list :", di)

# converting into heap
hq.heapify(di)

print("Heapified list of tuples :", di)

# converting heap to dictionary
di = dict(di)

print("Dictionary as heap :", di)
```

**Output**

```py
dictionary into list : [(11, 121), (2, 4), (5, 25), (3, 9)]
Heapified list of tuples : [(2, 4), (3, 9), (5, 25), (11, 121)]
Dictionary as heap : {2: 4, 3: 9, 5: 25, 11: 121}
```

**示例 2:基于字符串的键**

考虑一个字典，其中字母组合作为关键字，它们的编号作为值。例如:“**ABC”:123。**这必须在堆中维护。

## 蟒蛇 3

```py
# import modules
import heapq as hq

# dictionary to be heapified
dict_1 = {"yz": 2526, "ab": 12, "cd": 34, "ij": 910, "fg": 67}

# convert dictionary to list of tuples
di = list(dict_1.items())

print("dictionary into list :", di)

# converting into heap
hq.heapify(di)

print("Heapified list of tuples :", di)

# converting heap to dictionary
di = dict(di)

print("Dictionary as heap :", di)
```

**输出:**

> 字典成列表:[('yz '，2526)、(' ab '，12)、(' cd '，34)、(' ij '，910)、(' fg '，67)]
> 元组的 Heapified 列表:[('ab '，12)、(' fg '，67)、(' cd '，34)、(' ij '，910)、(' yz '，2526)】
> 字典成堆:{'ab': 12，' fg': 67，' cd': 34，' ij ':

**例 3:基于** **值**

这里的方法略有不同。要执行的步骤是:

1.  提取字典中的值并添加到列表中。
2.  将列表传递给 **heapify()。**
3.  基于堆化的列表值，通过迭代从原始字典重建一个新字典。

这里只有值满足堆属性，而不一定是键。

**示例:**

## 蟒蛇 3

```py
# import the module
import heapq as hq

# dictionary to be heapified
li_dict={11:121,2:4,5:25,3:9}

# List to hold values from dictionary
heap_dict=[]

# extract the values from dictionary
for i in li_dict.values():
    heap_dict.append(i)

# heapify the values
hq.heapify(heap_dict)  
print("Values of the dict after heapification :",heap_dict)

# list to hold final heapified dictionary
new_dict=[]

# mapping and reconstructing final dictionary
for i in range(0,len(heap_dict)):

    # Iterating the oringinal dictionary
    for k,v in li_dict.items():

        if v==heap_dict[i] and (k,v) not in new_dict:
            new_dict.append((k,v))

new_dict=dict(new_dict)

print("Final dictionary :",new_dict)
```

**Output**

```py
Values of the dict after heapification : [4, 9, 25, 121]
Final dictionary : {2: 4, 3: 9, 5: 25, 11: 121}
```