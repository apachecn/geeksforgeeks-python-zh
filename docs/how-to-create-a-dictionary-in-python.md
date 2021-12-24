# 如何用 Python 创建字典

> 原文:[https://www . geesforgeks . org/如何创建 python 词典/](https://www.geeksforgeeks.org/how-to-create-a-dictionary-in-python/)

**[字典](https://www.geeksforgeeks.org/python-dictionary/)** 是 Python 中的基础数据结构，对于 Python 程序员来说非常重要。它们是数据值的无序集合，用于像地图一样存储数据值。字典是可变的，这意味着它们可以改变。它们的时间复杂度为`O(1)`，并且针对内存开销和查找速度效率进行了大量优化。

**示例 1:** 每个子列表的第一个元素是键，第二个元素是值。我们希望动态存储键值对。

```
# Python program to demonstrate
# dynamic dictionary creation

# Initialize an empty dictionary
D = {} 

L = [['a', 1], ['b', 2], ['a', 3], ['c', 4]]

# Loop to add key-value pair
# to dictionary
for i in range(len(L)):
    # If the key is already 
    # present in dictionary
    # then append the value 
    # to the list of values
    if L[i][0] in D:
        D[L[i][0]].append(L[i][1])

    # If the key is not present
    # in the dictionary then add
    # the key-value pair
    else:
        D[L[i][0]]= []
        D[L[i][0]].append(L[i][1])

print(D) 
```

**输出:**

```
{'a': [1, 3], 'b': [2], 'c': [4]}

```

**例 2:**

```
# Python program to demonstrate
# dynamic dictionary creation

# Key to be added
key_ref = 'More Nested Things'
my_dict = {
    'Nested Things': [{'name', 'thing one'}, {'name', 'thing two'}]
}

# Value to be added
my_list_of_things = [{'name', 'thing three'}, {'name', 'thing four'}]

# try-except to take care of errors
# while adding key-value pair
try:
    my_dict[key_ref].append(my_list_of_things)

except KeyError:
    my_dict = {**my_dict, **{key_ref: my_list_of_things}}

print(my_dict)
```

**输出:**

```
{
 'Nested Things': [{'name', 'thing one'}, {'thing two', 'name'}], 
 'More Nested Things': [{'name', 'thing three'}, {'thing four', 'name'}]
}

```