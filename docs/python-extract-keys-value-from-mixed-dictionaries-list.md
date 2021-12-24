# Python–从混合字典列表中提取关键字的值

> 原文:[https://www . geesforgeks . org/python-extract-key-value-from-mixed-dictionary-list/](https://www.geeksforgeeks.org/python-extract-keys-value-from-mixed-dictionaries-list/)

给定一个字典列表，每个字典有不同的关键字，提取关键字 k 的值

> **输入**:test _ list =[{“Gfg”:3，“b”:7 }、{“is”:5、' a' : 10}、{“Best”:9、' c' : 11}]、K = 'b'
> **输出** : 7
> **解释**:b 的值为 7。
> 
> **输入**:test _ list =[{“Gfg”:3，“b”:7 }、{“is”:5、' a' : 10}、{“Best”:9、' c' : 11}]、K = 'c'
> **输出** : 11
> **解释**:c 的值为 11。

**方法一:使用列表理解**

这是执行这项任务的方法之一。在这种情况下，我们对列表中的每个字典进行迭代，并检查其中的键，如果存在，则返回所需的值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Key's value from Mixed Dictionaries List
# Using list comprehension

# initializing list
test_list = [{"Gfg" : 3, "b" : 7},
             {"is" : 5, 'a' : 10},
             {"Best" : 9, 'c' : 11}]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 'Best'

# list comprehension to get key's value
# using in operator to check if key is present in dictionary
res = [sub[K] for sub in test_list if K in sub][0]

# printing result
print("The extracted value : " + str(res))
```

**Output**

```
The original list : [{'Gfg': 3, 'b': 7}, {'is': 5, 'a': 10}, {'Best': 9, 'c': 11}]
The extracted value : 9
```

**方法 2:使用 update() +循环**

这是执行这项任务的另一种方式。在这种情况下，我们将每个字典更新为彼此。形成一个大字典，然后从这个字典中提取值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Key's value from Mixed Dictionaries List
# Using update() + loop

# initializing list
test_list = [{"Gfg" : 3, "b" : 7},
             {"is" : 5, 'a' : 10},
             {"Best" : 9, 'c' : 11}]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 'Best'

res = dict()
for sub in test_list:

    # merging all Dictionaries into 1
    res.update(sub)

# printing result
print("The extracted value : " + str(res[K]))
```

**Output**

```
The original list : [{'Gfg': 3, 'b': 7}, {'is': 5, 'a': 10}, {'Best': 9, 'c': 11}]
The extracted value : 9
```