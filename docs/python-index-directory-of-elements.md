# Python–元素索引目录

> 原文:[https://www . geesforgeks . org/python-index-元素目录/](https://www.geeksforgeeks.org/python-index-directory-of-elements/)

给定一个元素列表，任务是编写一个 python 程序来计算所有元素的所有索引。

**示例:**

```py
Input: test_list = [7, 6, 3, 7, 8, 3, 6, 7, 8]
Output: {8: [4, 8], 3: [2, 5], 6: [1, 6], 7: [0, 3, 7]}
Explanation: 8 occurs at 4th and 8th index, 3 occurs at 2nd and 5th index and so on.

Input: test_list = [7, 6, 3, 7, 8, 3, 6]
Output: {8: [4], 3: [2, 5], 6: [1, 6], 7: [0, 3]}
Explanation: 8 occurs at 4th index, 3 occurs at 2nd and 5th index and so on.
```

**方法一:**利用词典理解+ [枚举()](https://www.geeksforgeeks.org/enumerate-in-python/) + [集合()](https://www.geeksforgeeks.org/python-set-method/)

在这种情况下，我们使用*枚举()*来获取所有索引，并将其附加到索引列表中以进行值匹配。字典理解用于列表中所有元素的迭代。*集()*用于不重复获取所有元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Index Directory of Elements
# Using dictionary comprehension + enumerate()

# initializing list
test_list = [7, 6, 3, 7, 8, 3, 6, 7, 8]

# printing original list
print("The original list is : " + str(test_list))

# getting each element index values
res = {key: [idx for idx, val in enumerate(test_list) if val == key]
       for key in set(test_list)}

# printing result
print("Index Directory : " + str(res))
```

**输出:**

```py
The original list is : [7, 6, 3, 7, 8, 3, 6, 7, 8]
Index Directory : {8: [4, 8], 3: [2, 5], 6: [1, 6], 7: [0, 3, 7]}
```

**方法 2 :** 使用字典理解+[group by()](https://www.geeksforgeeks.org/itertools-groupby-in-python/)+[enumerate()](https://www.geeksforgeeks.org/enumerate-in-python/)+[sorted()](https://www.geeksforgeeks.org/sorted-function-python/)+item getter()

在这里，我们使用 *groupby()* 和 *sorted()* 对相似的元素进行排序和分组。 *itemgetter()* 用于从索引中获取按值排序的值，以及使用 *enumerate()* 提取的值。字典理解用于获得分组结果的成对索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Index Directory of Elements

# Using dictionary comprehension + groupby() + 
# enumerate() + sorted() + itemgetter()
from itertools import groupby
from operator import itemgetter

# initializing list
test_list = [7, 6, 3, 7, 8, 3, 6, 7, 8]

# printing original list
print("The original list is : " + str(test_list))

# after grouping after sorting
# and rearranging and assigning values with index
res = {key: [idx for idx, _ in groups] for key, groups in groupby(
    sorted(enumerate(test_list), key=itemgetter(1)), key=itemgetter(1))}

# printing result
print("Index Directory : " + str(res))
```

**输出:**

```py
The original list is : [7, 6, 3, 7, 8, 3, 6, 7, 8]
Index Directory : {3: [2, 5], 6: [1, 6], 7: [0, 3, 7], 8: [4, 8]}
```