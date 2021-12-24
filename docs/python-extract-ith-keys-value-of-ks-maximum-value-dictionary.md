# Python–提取 K 最大值字典的带键值

> 原文:[https://www . geesforgeks . org/python-extract-with-keys-value-of-ks-maximum-value-dictionary/](https://www.geeksforgeeks.org/python-extract-ith-keys-value-of-ks-maximum-value-dictionary/)

给定字典列表，根据第 k 个关键字的最大值提取第 I 个关键字值。

> **输入**:test _ list =[{“Gfg”:3、“is”:9、“best”:10 }、{“Gfg”:8、“is”:11、“best”:19 }、{“Gfg”:9、“is”:16、“best”:1 }]、K =“best”、I =“is”
> **输出** : 11
> **解释** : best 在 19 时为 max，其对应的“is”值为 11。
> 
> **输入**:test _ list =[{“Gfg”:3、“is”:9、“best”:10 }、{“Gfg”:8、“is”:11、“best”:19 }、{“Gfg”:9、“is”:16、“best”:1 }]、K =“Gfg”、I =“is”
> **输出** : 16
> **解释** : Gfg 在 9 时为 max，其对应的“is”值为 16。

**方法#1:使用 max() + lambda**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 max()和 lambda 提取 kth 密钥的 max。然后从提取的字典中提取出第一个关键字。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract ith Key's Value of K's Maximum value dictionary
# Using max() + lambda

# initializing lists
test_list = [{"Gfg" : 3, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 9, "is" : 16, "best" : 1}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = "best"

# initializing i 
i = "Gfg"

# using get() to handle missing key, assigning lowest value
res = max(test_list, key = lambda ele : ele.get(K, 0))[i]

# printing result 
print("The required value : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': 3, 'is': 9, 'best': 10}, {'Gfg': 8, 'is': 11, 'best': 19}, {'Gfg': 9, 'is': 16, 'best': 1}]
The required value : 8

```

**方法 2:使用 max() +外部功能**

这是解决这个问题的另一种方法。这种计算方式与上面的方法类似，不同的是使用了自定义比较器，而不是 lambda 函数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract ith Key's Value of K's Maximum value dictionary
# Using max() + external function

# custom function as comparator
def cust_fnc(ele):
    return ele.get(K, 0) 

# initializing lists
test_list = [{"Gfg" : 3, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 9, "is" : 16, "best" : 1}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = "best"

# initializing i 
i = "Gfg"

# using get() to handle missing key, assigning lowest value
res = max(test_list, key = cust_fnc)[i]

# printing result 
print("The required value : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': 3, 'is': 9, 'best': 10}, {'Gfg': 8, 'is': 11, 'best': 19}, {'Gfg': 9, 'is': 16, 'best': 1}]
The required value : 8

```