# Python–提取值总和大于 K 的字典

> 原文:[https://www . geesforgeks . org/python-extract-dictionary-with-values-sum-大于-k/](https://www.geeksforgeeks.org/python-extract-dictionaries-with-values-sum-greater-than-k/)

给定一个字典列表，提取所有关键字总和超过 k 的字典。

> **输入**:test _ list =[{“Gfg”:4、“is”:8、“best”:9 }、{“Gfg”:3、“is”:7、“best”:5 }]、K = 15
> **输出**:[{“Gfg”:4、“is”:8、“best”:9 }]
> **解释** : 4 + 9 + 8 = 21。大于 K，因此返回。
> 
> **输入**:test _ list =[{“Gfg”:4、“is”:8、“best”:9 }、{“Gfg”:3、“is”:7、“best”:5 }]，K = 25
> **输出** : []
> **解释**:无字典带和> 25。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们对所有字典进行迭代，并提取每个字典的总和，超过 K，我们将它们过滤掉。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract dictionaries with values sum greater than K
# Using 

# initializing lists
test_list = [{"Gfg" : 4, "is" : 8, "best" : 9},
             {"Gfg" : 5, "is": 8, "best" : 1},
             {"Gfg" : 3, "is": 7, "best" : 6}, 
             {"Gfg" : 3, "is": 7, "best" : 5}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 15

# using loop to extract all dictionaries
res = []
for sub in test_list:
    sum = 0
    for key in sub:
        sum += sub[key]
    if sum > K:
        res.append(sub)

# printing result 
print("Dictionaries with summation greater than K : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': 4, 'is': 8, 'best': 9}, {'Gfg': 5, 'is': 8, 'best': 1}, {'Gfg': 3, 'is': 7, 'best': 6}, {'Gfg': 3, 'is': 7, 'best': 5}]
Dictionaries with summation greater than K : [{'Gfg': 4, 'is': 8, 'best': 9}, {'Gfg': 3, 'is': 7, 'best': 6}]

```

**方法 2:使用列表理解+求和()**

这是完成这项任务的一种线性方式。在这种情况下，我们使用 sum()执行求和任务，列表理解可用于执行将所有逻辑组合成单行的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract dictionaries with values sum greater than K
# Using list comprehension + sum()

# initializing lists
test_list = [{"Gfg" : 4, "is" : 8, "best" : 9},
             {"Gfg" : 5, "is": 8, "best" : 1},
             {"Gfg" : 3, "is": 7, "best" : 6}, 
             {"Gfg" : 3, "is": 7, "best" : 5}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 15

# using one-liner to extract all the dictionaries
res = [sub for sub in test_list if sum(list(sub.values())) > K]

# printing result 
print("Dictionaries with summation greater than K : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': 4, 'is': 8, 'best': 9}, {'Gfg': 5, 'is': 8, 'best': 1}, {'Gfg': 3, 'is': 7, 'best': 6}, {'Gfg': 3, 'is': 7, 'best': 5}]
Dictionaries with summation greater than K : [{'Gfg': 4, 'is': 8, 'best': 9}, {'Gfg': 3, 'is': 7, 'best': 6}]

```