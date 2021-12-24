# Python |字典中的关键索引

> 原文:[https://www . geesforgeks . org/python-key-index-in-dictionary/](https://www.geeksforgeeks.org/python-key-index-in-dictionary/)

字典的概念类似于 C++语言中的映射数据结构的概念，只是字典中的键与它的排序无关，即它不像 C++中的键在内部排序那样排序。这就提出了一个问题，我们可能需要在字典中找到键的确切位置。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `enumerate()`**
以上功能组合在一起可以执行这个特定的任务。在这种情况下，首先将字典转换成一对元组，然后检查作为关键字的元组的第一个元素的索引。

```py
# Python3 code to demonstrate working of
# Key index in Dictionary
# Using list comprehension + enumerate()

# initializing dictionary
test_dict = {'all' : 1, 'food' : 2, 'good' : 3, 'have' : 4}

# initializing search key string
search_key = 'good'

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using list comprehension + enumerate()
# Key index in Dictionary
temp = list(test_dict.items()) 
res = [idx for idx, key in enumerate(temp) if key[0] == search_key]

# printing result 
print("Index of search key is : " + str(res))
```

**Output :**

```py
The original dictionary is : {'have': 4, 'all': 1, 'good': 3, 'food': 2}
Index of search key is : [2]

```