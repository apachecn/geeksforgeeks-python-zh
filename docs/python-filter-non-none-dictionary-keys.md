# Python–过滤非无字典键

> 原文:[https://www . geesforgeks . org/python-filter-non-none-dictionary-keys/](https://www.geeksforgeeks.org/python-filter-non-none-dictionary-keys/)

很多时候，在使用字典时，我们希望获得非空键的键。这在机器学习中得到了应用，在机器学习中，我们必须输入没有任何值的数据。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
在这种情况下，我们只是对所有键运行一个循环，并检查值，如果不是无，我们将所有非无键的键追加到一个存储列表中。

```py
# Python3 code to demonstrate working of
# Non-None dictionary Keys
# Using loop

# initializing dictionary
test_dict = {'Gfg' : 1, 'for' : 2, 'CS' : None}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using loop
# Non-None dictionary Keys
res = []
for ele in test_dict:
    if test_dict[ele] is not None :
        res.append(ele)

# printing result 
print("Non-None keys list : " + str(res))
```

**Output :**

```py
The original dictionary is : {'for': 2, 'CS': None, 'Gfg': 1}
Non-None keys list : ['for', 'Gfg']

```