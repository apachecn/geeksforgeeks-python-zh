# Python–使用有序值过滤字典

> 原文:[https://www . geesforgeks . org/python-filter-dictionary-with-ordered-values/](https://www.geeksforgeeks.org/python-filter-dictionaries-with-ordered-values/)

给定字典列表，任务是编写一个 python 程序来过滤具有递增顺序(即排序)值的字典。

**示例:**

> **输入** : test_list = [{'gfg' : 2，' is' : 8，' good' : 10}、{'gfg' : 1，' for' : 10、' geeks' : 9}、{'love' : 3、' gfg' : 4}]
> **输出** : [{'gfg': 2、' is': 8、' good': 10}、{'love': 3、' gfg': 4}]
> **解释** : 2、8、10 依次递增。
> 
> **输入** : test_list = [{'gfg' : 2，' is' : 8，' good' : 10}，{'gfg' : 1，' for' : 10，' geeks' : 9}，{'love' : 4，' gfg' : 3}]
> **输出** : [{'gfg': 2，' is': 8，' good': 10}]
> **解释** : 2，8，10 依次递增。

**方法#1:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/) **+** [**值()**](https://www.geeksforgeeks.org/python-dictionary-values/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在本文中，我们使用 sorted()执行排序任务，并使用 values()提取值，使用列表理解来执行所有字典的迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter dictionaries with ordered values
# Using sorted() + values() + list comprehension

# initializing list
test_list = [{'gfg': 2, 'is': 8, 'good': 10},
             {'gfg': 1, 'for': 10, 'geeks': 9},
             {'love': 3, 'gfg': 4}]

# printing original list
print("The original list is : " + str(test_list))

# sorted to check with ordered values
# values() extracting dictionary values
res = [sub for sub in test_list if sorted(
    list(sub.values())) == list(sub.values())]

# printing result
print("The filtered Dictionaries : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 2，' is': 8，' good': 10}，{'gfg': 1，' for': 10，' geeks': 9}，{'love': 3，' gfg': 4}]
> 筛选后的词典:[{'gfg': 2，' is': 8，' good': 10}，{'love': 3，' gfg': 4}]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+排序()**

在本例中，我们使用 filter()执行过滤任务，lambda 函数用于执行注入检查递增值所需的功能的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter dictionaries with ordered values
# Using filter() + lambda + sorted()

# initializing list
test_list = [{'gfg': 2, 'is': 8, 'good': 10},
             {'gfg': 1, 'for': 10, 'geeks': 9},
             {'love': 3, 'gfg': 4}]

# printing original list
print("The original list is : " + str(test_list))

# sorted to check with ordered values
# values() extracting dictionary values
# filter() and lambda function used to filter
res = list(filter(lambda sub: sorted(list(sub.values()))
                  == list(sub.values()), test_list))

# printing result
print("The filtered Dictionaries : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 2，' is': 8，' good': 10}，{'gfg': 1，' for': 10，' geeks': 9}，{'love': 3，' gfg': 4}]
> 筛选后的词典:[{'gfg': 2，' is': 8，' good': 10}，{'love': 3，' gfg': 4}]