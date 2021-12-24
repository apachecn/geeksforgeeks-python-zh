# Python–值总和等于 K 的字典键

> 原文:[https://www . geesforgeks . org/python-dictionary-keys-what-values-summary-equals-k/](https://www.geeksforgeeks.org/python-dictionary-keys-whose-values-summation-equals-k/)

给定一个字典和值 K，提取值总和等于 K 的键

> **输入**:{“Gfg”:3，“is”:5，“Best”:9，“for”:8，“Geeks”:10 }，K = 17
> **输出**:[‘Best’，‘for’]
> **解释** : 9 + 8 = 17，因此那些键被提取。
> 
> **输入**:{“Gfg”:3，“is”:5，“Best”:9，“for”:8，“Geeks”:10 }，K = 19
> **输出**:[“Best”，“Geeks”]
> **解释** : 9 + 10 = 19，因此那些键被提取。

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们迭代所有的键，以及内部列表中的下一个键，并继续检查值的总和。如果等于 k，则存储密钥。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary Keys whose Values summation equals K 
# Using loop

# initializing dictionary
test_dict = {"Gfg" : 3, "is" : 5, "Best" : 9, "for" : 8, "Geeks" : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 14

# extracting keys and values
keys = list(test_dict.keys())
values = list(test_dict.values())

res = None
for i in range(len(keys)):
    for j in range(i + 1, len(keys)):

        # checking if values equals K
        if values[i] + values[j] == K:
            res = [keys[i], keys[j]]

# printing result 
print("Keys whose sum equals K : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 3, 'is': 5, 'Best': 9, 'for': 8, 'Geeks': 10}
Keys whose sum equals K : ['is', 'Best']

```

**方法 2:使用列表理解**

这是执行这项任务的另一种方式。在这种情况下，我们使用列表理解以速记方式执行类似于上述方法的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary Keys whose Values summation equals K 
# Using list comprehension 

# initializing dictionary
test_dict = {"Gfg" : 3, "is" : 5, "Best" : 9, "for" : 8, "Geeks" : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 14

# extracting keys and values
keys = list(test_dict.keys())
values = list(test_dict.values())

# checking for keys in one liner
res = [[keys[i], keys[j]]  for i in range(len(keys)) for j in range(i + 1, len(keys)) if values[i] + values[j] == K]

# printing result 
print("Keys whose sum equals K : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 3, 'is': 5, 'Best': 9, 'for': 8, 'Geeks': 10}
Keys whose sum equals K : [['is', 'Best']]

```