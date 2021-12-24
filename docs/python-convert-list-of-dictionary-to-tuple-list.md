# Python |将字典列表转换为元组列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-dictionary-to-tuple-list/](https://www.geeksforgeeks.org/python-convert-list-of-dictionary-to-tuple-list/)

给定一个字典列表，编写一个 python 代码将字典列表转换成 if 元组列表。

**示例:**

```
Input: 
[{'a':[1, 2, 3], 'b':[4, 5, 6]}, 
 {'c':[7, 8, 9], 'd':[10, 11, 12]}]

Output: 
[('b', 4, 5, 6), ('a', 1, 2, 3), ('d', 10, 11, 12), ('c', 7, 8, 9)]

Input: 
[{'a':['America', 'Australia'], 'b':['Bhutan', 'Bhopal']},
 {'c':['Canada', 'California'], 'd':['Denmark', 'Delhi']}]

Output: 
[('a', 'America', 'Australia'), ('b', 'Bhutan', 'Bhopal'),
 ('c', 'Canada', 'California'), ('d', 'Denmark', 'Delhi')]

```

下面是将字典列表转换为元组列表的各种方法。

**方法#1:使用天真方法**

```
# Python code to demonstrate
# converting list of dictionary to list of tuples

# initialising list of dictionary
ini_list = [{'a':[1, 2, 3], 'b':[4, 5, 6]},
            {'c':[7, 8, 9], 'd':[10, 11, 12]}]

# converting to list of tuples
temp_dict = {}
result = []
for ini_dict in ini_list:
    for key in ini_dict.keys():
         if key in temp_dict:
             temp_dict[key] += ini_dict[key]
         else:
             temp_dict[key] = ini_dict[key]

for key in temp_dict.keys():
     result.append(tuple([key] + temp_dict[key]))

# printing result
print ("Resultant list of tuples: {}".format(result))
```

**输出:**

```
Resultant list of tuples: [('a', 1, 2, 3), ('d', 10, 11, 12), ('b', 4, 5, 6), ('c', 7, 8, 9)]

```

**方法二:使用列表理解**

```
# Python code to demonstrate
# converting list of dictionary to list of tuples

# initialising list of dictionary
ini_list = [{'a':[1, 2, 3], 'b':[4, 5, 6]},
            {'c':[7, 8, 9], 'd':[10, 11, 12]}]

# converting to list of tuples
dict_list = [(key, )+tuple(val) for dic in ini_list 
                       for key, val in dic.items()]

# printing result
print ("Resultant list of tuples: {}".format(dict_list))
```

**输出:**

```
Resultant list of tuples: [('b', 4, 5, 6), ('a', 1, 2, 3), ('d', 10, 11, 12), ('c', 7, 8, 9)]

```