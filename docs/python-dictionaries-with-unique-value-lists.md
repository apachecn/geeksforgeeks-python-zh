# Python–具有唯一值列表的字典

> 原文:[https://www . geesforgeks . org/python-带有唯一值列表的词典/](https://www.geeksforgeeks.org/python-dictionaries-with-unique-value-lists/)

给定带有列表值的字典列表，提取唯一的字典。

> **输入** : [{'Gfg': [2，3]，' is' : [7，8]，' best' : [10]}，{'Gfg': [2，3]，' is' : [7，8]，' best' : [10]，' best' : [10]}]
> **输出** : [{'Gfg': [2，3]，' is': [7，8]，' best': [10]}]
> **解释:**两者为相似词典，故 1 为
> 
> **输入** : [{'Gfg': [2，3]，' is' : [7，8]，' best' : [10]}，{'Gfg': [2，3]，' is' : [7，8]，' best' : [10，11]}]
> **输出** : [{'Gfg': [2，3]，' is': [7，8]，' best': [10]}，{'Gfg': [2，3]，' is ':[7]

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们对每个字典进行迭代和记忆，并防止它添加到结果中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Unique Value Lists Dictionaries
# Using loop

# initializing lists
test_list = [{'Gfg':  [2, 3], 'is' : [7, 8], 'best' : [10]}, 
             {'Gfg':  [2, 3], 'is' : [7], 'best' : [10]}, 
             {'Gfg':  [2, 3], 'is' : [7, 8], 'best' : [10]}]

# printing original list
print("The original list : " + str(test_list))

# Using loop to iterate through elements
# result array to also keep track of already occurred elements
res = []
for sub in test_list:
    if sub not in res:
        res.append(sub)

# printing result 
print("List after duplicates removal : " + str(res))
```

**Output**

```
The original list : [{'Gfg': [2, 3], 'is': [7, 8], 'best': [10]}, {'Gfg': [2, 3], 'is': [7], 'best': [10]}, {'Gfg': [2, 3], 'is': [7, 8], 'best': [10]}]
List after duplicates removal : [{'Gfg': [2, 3], 'is': [7, 8], 'best': [10]}, {'Gfg': [2, 3], 'is': [7], 'best': [10]}]

```

**方法 2:使用列表理解**

这是执行这项任务的另一种方式。在这种情况下，采用了与上面类似的方法，只是封装结果的不同导致了对一行的列表理解。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Unique Value Lists Dictionaries
# Using list comprehension

# initializing lists
test_list = [{'Gfg':  [2, 3], 'is' : [7, 8], 'best' : [10]}, 
             {'Gfg':  [2, 3], 'is' : [7], 'best' : [10]}, 
             {'Gfg':  [2, 3], 'is' : [7, 8], 'best' : [10]}]

# printing original list
print("The original list : " + str(test_list))

# list comprehension to encapsulate logic in one liner
res = []
[res.append(val) for val in test_list if val not in res]

# printing result 
print("List after duplicates removal : " + str(res))
```

**Output**

```
The original list : [{'Gfg': [2, 3], 'is': [7, 8], 'best': [10]}, {'Gfg': [2, 3], 'is': [7], 'best': [10]}, {'Gfg': [2, 3], 'is': [7, 8], 'best': [10]}]
List after duplicates removal : [{'Gfg': [2, 3], 'is': [7, 8], 'best': [10]}, {'Gfg': [2, 3], 'is': [7], 'best': [10]}]

```