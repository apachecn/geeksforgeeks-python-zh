# Python |访问字典中的键值

> 原文:[https://www . geesforgeks . org/python-access-key-value-in-dictionary/](https://www.geeksforgeeks.org/python-accessing-key-value-in-dictionary/)

[字典](https://www.geeksforgeeks.org/python-dictionary/)是编程中相当有用的一种数据结构，通常用于用值对特定的键进行散列，以便可以高效地检索它们。

让我们讨论在 Python 字典中访问所有键及其值的各种方法。

**方法#1 :** 使用`in`运算符

最常用的方法是获取所有键及其值，`in`运算符被广泛用于此目的，强烈推荐使用，因为它提供了一种实现此任务的简洁方法。

```py
# Python3 code to demonstrate 
# to get key and value
# using in operator

# initializing dictionary
test_dict = {"Geeks" : 1, "for" : 2, "geeks" : 3}

# Printing dictionary
print ("Original dictionary is : " + str(test_dict))

# using in operator to
# get key and value
print ("Dict key-value are : ")
for i in test_dict :
    print(i, test_dict[i])
```

**Output:**

```py
Original dictionary is : {'geeks': 3, 'for': 2, 'Geeks': 1}
Dict key-value are : 
geeks 3
for 2
Geeks 1

```

**方法 2 :** 使用列表理解

该方法也使用了与上述方法类似的方法，只是将逻辑绑定到一个列表中，并将字典的键值对作为列表中键值的元组返回。

```py
# Python3 code to demonstrate 
# to get key and value
# using list comprehension

# initializing dictionary
test_dict = {"Geeks" : 1, "for" : 2, "geeks" : 3}

# Printing dictionary
print ("Original dictionary is : " + str(test_dict))

# using list comprehension to
# get key and value
print ("Dict key-value are : ")
print([(k, test_dict[k]) for k in test_dict])
```

**Output:**

```py
Original dictionary is : {'Geeks': 1, 'for': 2, 'geeks': 3}
Dict key-value are : 
[('Geeks', 1), ('for', 2), ('geeks', 3)]

```

**方法 3 :** 使用`dict.items()`

`items()`，in dictionary 遍历所有的键，帮助我们在循环中一个接一个的访问`key-value`对，也是一个很好的带值访问字典键的方法。

```py
# Python3 code to demonstrate 
# to get key and value
# using dict.items()

# initializing dictionary
test_dict = {"Geeks" : 1, "for" : 2, "geeks" : 3}

# Printing dictionary
print ("Original dictionary is : " + str(test_dict))

# using dict.items() to
# get key and value
print ("Dict key-value are : ")
for key, value in test_dict.items():
    print (key, value)
```

**Output:**

```py
Original dictionary is : {'geeks': 3, 'for': 2, 'Geeks': 1}
Dict key-value are : 
geeks 3
for 2
Geeks 1

```

**方法#4 :** 使用`enumerate()`

Python 还提供了`enumerate()`来帮助迭代各种容器，无论是字典还是列表。这个功能的力量也可以用来执行这个任务。它还有助于访问字典中该对位置的命名索引。

```py
# Python3 code to demonstrate 
# to get key and value
# using enumerate()

# initializing dictionary
test_dict = {"Geeks" : 1, "for" : 2, "geeks" : 3}

# Printing dictionary
print ("Original dictionary is : " + str(test_dict))

# using enumerate() to
# get key and value
print ("Dict key-value are : ")
for i in enumerate(test_dict.items()):
    print (i)
```

**Output:**

```py
Original dictionary is : {'geeks': 3, 'Geeks': 1, 'for': 2}
Dict key-value are : 
(0, ('geeks', 3))
(1, ('Geeks', 1))
(2, ('for', 2))

```