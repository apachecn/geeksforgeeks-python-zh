# Python |检查给定的多个键是否存在于字典中

> 原文:[https://www . geesforgeks . org/python-check-if-given-multi-key-in-a-dictionary/](https://www.geeksforgeeks.org/python-check-if-given-multiple-keys-exist-in-a-dictionary/)

Python 中的[字典由键值对的集合组成。每个键值对将键映射到其关联的值。](https://www.geeksforgeeks.org/python-dictionary/)

> 输入:dict[]= {“geeksforgeeks”:1，“练习”:2，“贡献”:3}
> 键[]= {“geeksforgeeks”，“练习”}
> 输出:是
> 
> 输入:dict[]= {“geeksforgeeks”:1、“练习”:2、“贡献”:3}
> 键[]= {“geeksforgeeks”、“ide”}
> 输出:否

让我们讨论检查字典中多个键的各种方法:

**方法#1** 使用比较运算符:
这是一种常见的方法，我们创建一个包含用于比较的键的集合，并使用比较运算符检查该键是否存在于我们的字典中。

```py
# Python3 code to check multiple key existence
# using comparison operator

# initializing a dictionary
sports = {"geeksforgeeks" : 1, "practice" : 2, "contribute" :3}

# using comparison operator
print(sports.keys() >= {"geeksforgeeks", "practice"})
print(sports.keys() >= {"contribute", "ide"})
```

**Output:**

```py
True
False

```

**方法 2** 使用 issubset() :
在这个方法中，我们将检查我们要比较的键是否是字典中键的`subset()`。

```py
# Python3 code heck multiple key existence
# using issubset

# initializing a dictionary
sports = {"geeksforgeeks" : 1, "practice" : 2, "contribute" :3}

# creating set of keys that we want to compare
s1 = set(['geeksforgeeks', 'practice'])
s2 = set(['geeksforgeeks', 'ide'])

print(s1.issubset(sports.keys()))
print(s2.issubset(sports.keys()))
```

**Output:**

```py
True
False

```

**方法#3** 使用 if 和 all 语句:
在这个方法中，我们将检查我们想要比较的所有关键元素是否都存在于我们的字典中。

```py
# Python3 code check multiple key existence
# using if and all

# initializing a dictionary
sports = {"geeksforgeeks" : 1, "practice" : 2, "contribute" :3}

# using if, all statement 
if all(key in sports for key in ('geeksforgeeks', 'practice')):
    print("keys are present")
else:
    print("keys are not present")

# using if, all statement 
if all(key in sports for key in ('geeksforgeeks', 'ide')):
    print("keys are present")
else:
    print("keys are not present")
```

**Output:**

```py
keys are present
keys are not present

```