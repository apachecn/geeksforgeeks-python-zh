# Python |提取过滤后的字典值

> 原文:[https://www . geesforgeks . org/python-extract-filtered-dictionary-values/](https://www.geeksforgeeks.org/python-extract-filtered-dictionary-values/)

在使用 Python 字典时，可能会出现这样的情况:我们只关心获取筛选值列表，而不关心键。这是另一个重要的用途，应该了解并讨论解决方案。让我们通过某些方法来执行这个任务。

**方法#1:使用循环+ `keys()`**
实现这个任务想到的第一个方法是使用循环访问每个过滤后的键的值，并将其追加到列表中并返回。这可以是执行该任务的方法之一。

```
# Python3 code to demonstrate working of
# Extract filtered Dictionary Values
# Using loop + keys()

# initializing dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 2

# Extract filtered Dictionary Values
# Using loop + keys()
res = []
for key in test_dict.keys() :
    if test_dict[key] >= K:
        res.append(test_dict[key])

# printing result
print("The list of filtered values is : " + str(res))
```

**Output :**

```
The original dictionary is : {'best': 3, 'gfg': 1, 'is': 2}
The list of filtered values is : [3, 2]

```