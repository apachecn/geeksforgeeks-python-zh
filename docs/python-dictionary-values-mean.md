# Python–字典值平均值

> 原文:[https://www . geesforgeks . org/python-dictionary-values-mean/](https://www.geeksforgeeks.org/python-dictionary-values-mean/)

给定一个字典，找出所有存在值的平均值。

> **输入**:test _ dict = {“Gfg”:4、“is”:4、“Best”:4、“for”:4、“Geeks”:4 }
> **输出** : 4.0
> **解释** : (4 + 4 + 4 + 4 + 4) / 4 = 4.0，遂取均值。
> 
> **输入**:test _ dict = {“Gfg”:5、“is”:10、“Best”:15 }
> **输出** : 10.0
> **解释**:这些的平均值为 10.0

**方法#1:使用 loop + len()**

这是执行这项任务的粗暴方式。在这种情况下，我们遍历每个值并执行求和，然后将结果除以使用 len()提取的总密钥。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary Values Mean
# Using loop + len()

# initializing dictionary
test_dict = {"Gfg" : 4, "is" : 7, "Best" : 8, "for" : 6, "Geeks" : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# loop to sum all values 
res = 0
for val in test_dict.values():
    res += val

# using len() to get total keys for mean computation
res = res / len(test_dict)

# printing result 
print("The computed mean : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 4, 'is': 7, 'Best': 8, 'for': 6, 'Geeks': 10}
The computed mean : 7.0

```

**方法 2:使用 sum() + len() + values()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用总和()和使用 len()计算的总密钥大小()来执行求和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary Values Mean
# Using sum() + len() + values()

# initializing dictionary
test_dict = {"Gfg" : 4, "is" : 7, "Best" : 8, "for" : 6, "Geeks" : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# values extracted using values()
# one-liner solution to problem.
res = sum(test_dict.values()) / len(test_dict)

# printing result 
print("The computed mean : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 4, 'is': 7, 'Best': 8, 'for': 6, 'Geeks': 10}
The computed mean : 7.0

```