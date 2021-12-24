# Python |列表中某个元素的最后一次出现

> 原文:[https://www . geesforgeks . org/python-列表中某个元素的最后一次出现/](https://www.geeksforgeeks.org/python-last-occurrence-of-some-element-in-a-list/)

有很多方法可以找到列表中元素的第一个索引，因为 Python 在其语言中提供了`index()`函数，该函数返回列表中元素第一次出现的索引。但是，如果希望获得列表中最后一个出现的元素，通常需要使用更长的方法。

让我们讨论一下某些人手不足的人来完成这项特殊的任务。

**方法#1:使用`join() + rfind()`**
这通常是我们可以用来完成这个任务的黑客。连接整个列表，然后使用字符串函数`rfind()`从右侧获取第一个元素，即列表中元素的最后一个索引。

```
# Python3 code to demonstrate 
# to get last element occurrence
# using join() + rfind()

# initializing list
test_list = ['G', 'e', 'e', 'k', 's', 'f', 'o', 'r',
                            'g', 'e', 'e', 'k', 's']

# using join() + rfind()
# to get last element occurrence
res = ''.join(test_list).rindex('e')

# printing result
print ("The index of last element occurrence: " + str(res))
```

**Output:**

```
The index of last element occurrence: 10

```

**方法 2:使用列表切片+ `index()`**
使用列表切片我们反转列表，使用常规索引方法获取元素第一次出现的索引。由于反向列表，返回最后一个匹配项，而不是列表的第一个索引。

```
# Python3 code to demonstrate 
# to get last element occurrence
# using List Slice + index()

# initializing list
test_list = ['G', 'e', 'e', 'k', 's', 'f', 'o', 'r',
                            'g', 'e', 'e', 'k', 's']

# using List Slice + index()
# to get last element occurrence
res = len(test_list) - 1 - test_list[::-1].index('e')

# printing result
print ("The index of last element occurrence: " + str(res))
```

**Output:**

```
The index of last element occurrence: 10

```

**方法 3:使用`max() + enumerate()`**
我们使用枚举函数获得具有特定元素的所有元素的列表，然后使用`max()`获得最大值，即列表的最后一个索引。

```
# Python3 code to demonstrate 
# to get last element occurrence
# using max() + enumerate()

# initializing list
test_list = ['G', 'e', 'e', 'k', 's', 'f', 'o', 'r',
                            'g', 'e', 'e', 'k', 's']

# using max() + enumerate()
# to get last element occurrence
res = max(idx for idx, val in enumerate(test_list) 
                                    if val == 'e')

# printing result
print ("The index of last element occurrence: " + str(res))
```

**Output:**

```
The index of last element occurrence: 10

```