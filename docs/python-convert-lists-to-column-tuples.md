# Python |将列表转换为列元组

> 原文:[https://www . geesforgeks . org/python-convert-list-to-column-元组/](https://www.geeksforgeeks.org/python-convert-lists-to-column-tuples/)

有时，在处理数据时，我们会遇到一个问题，即我们需要在单个容器中获取相似的索引元素。这意味着矩阵/多重列表的列需要被转换成元组列表，每个元组都由相似的索引元素组成。让我们讨论一下完成这项任务的某些方法。

**方法一:使用`zip()` +列表理解**
以上功能的组合可以共同完成这个特定的任务。在这种情况下，我们使用 zip()将相似的索引元素组合成列，并将所有元组绑定到一个列表中，字典列表的迭代是通过列表理解来执行的。

```py
# Python3 code to demonstrate working of
# Convert Lists to column tuples
# using zip() + list comprehension

# initialize dictionary
test_dict = {'list1' : [1, 4, 5], 
             'list2' : [6, 7, 4],
             'list3' : [9, 1, 11]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Lists to column tuples
# using zip() + list comprehension
res = list(zip(*(test_dict[key] for key in test_dict.keys())))

# printing result
print("Like index column tuples are : " + str(res))
```

**Output :**

> 原字典为:{'list3': [9，1，11]，' list2': [6，7，4]，' list1': [1，4，5]}
> 同类索引列元组为:[(9，6，1)，(1，7，4)，(11，4，5)]