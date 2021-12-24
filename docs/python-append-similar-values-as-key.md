# Python–将相似值作为关键字追加

> 原文:[https://www . geesforgeks . org/python-append-相似值-as-key/](https://www.geeksforgeeks.org/python-append-similar-values-as-key/)

有时，在处理数据时，我们可能会遇到一些问题，需要将特定的列表和值归类到类似的键中。这可能是统计数据的问题。比如点票或者点硬币。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们运行一个循环来将值添加到字典值列表中，如果不存在，我们将动态创建密钥并执行追加。

```
# Python3 code to demonstrate working of 
# Append Similar Values as Key
# Using loop

# initializing list
test_list = ['Manjeet', 'Nikhil', 'Akshat', 'Akash', 
            'Manjeet', 'Akash', 'Akshat', 'Manjeet']

# printing original list
print("The original list is : " + str(test_list))

# Append Similar Values as Key
# Using loop
res = dict()
for ele in test_list:
    try:
        res[ele].append(ele)
    except KeyError:
        res[ele] = [ele]

# printing result 
print("The similar values dictionary is : " + str(res)) 
```

**Output :**

> 原列表为:['Manjeet '，' Nikhil '，' Akshat '，' Akash '，' Manjeet '，' Akash '，' Akshat '，' Manjeet']
> 相似值字典为:{'Nikhil': ['Nikhil '，' Manjeet': ['Manjeet '，' Manjeet '，' Manjeet']，' Akash': ['Akash '，' Akash '，' Akshat': ['Akshat '，' Akshat']