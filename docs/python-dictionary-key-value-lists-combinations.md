# Python–字典键值列表组合

> 原文:[https://www . geesforgeks . org/python-dictionary-key-value-list-组合拳/](https://www.geeksforgeeks.org/python-dictionary-key-value-lists-combinations/)

给定值为列表的字典，提取所有可能的组合，包括交叉键和值。

> **输入**:test _ dict = {“Gfg”:[4，5]，“is”:[1，2]，“Best”:[9，4]}
> **输出**:{ 0:[' Gfg '，4]，['is '，1]，['Best '，9]]，1: [['Gfg '，4]，['is '，1]，['Best '，4]]，2:[' Gfg '，4]，['is '，2]，['Best '
> 
> **输入** : test_dict = {"Gfg" : [4]，" is" : [1]，" Best" : [4]}
> **输出** : {0: [['Gfg '，4]，['is '，1]，['Best '，4]]}
> **解释**:也打印所有可能的带值和交叉值的组合键。

**方法一:使用 product() + zip() + loop**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 product()执行所有值的第一个组合键，使用 zip()和 loop 执行交叉组合键。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Dictionary Key Value lists combinations
# Using product() + zip() + loop
from itertools import product

# initializing dictionary
test_dict = {"Gfg" : [4, 5, 7],
             "is" : [1, 2, 9],
             "Best" : [9, 4, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

temp = list(test_dict.keys())        
res = dict()
cnt = 0

# making key-value combinations using product
for combs in product (*test_dict.values()):

    # zip used to perform cross keys combinations.
    res[cnt] = [[ele, cnt] for ele, cnt in zip(test_dict, combs)]
    cnt += 1

# printing result 
print("The computed combinations : " + str(res)) 
```

**Output**

> 原始字典为:{'Gfg': [4，5，7]，' is': [1，2，9]，' Best': [9，4，2]}
> 计算出的组合:{ 0:[' Gfg '，4]，['is '，1]，['Best '，9]，，1:[' Gfg '，4]，['Best '，4]，，2: [['Gfg '，4]，['is '，1]，['Best '，2]，，3:[[[ ['is '，9]，['Best '，2]]，9: [['Gfg '，5]，['is '，1]，['Best '，9]]，10:[' Gfg '，5]，['is '，1]，['Best '，4]]，11: [['Gfg '，5]，['is '，1]，['Best '，2]，，12:[' Gfg '，5]，['is '，2]，['Best '，9]，，13:[' Gfg '，5] 20:[' Gfg '，7]，['is '，1]，['Best '，2]]，21:[' Gfg '，7]，['is '，2]，['Best '，9]]，22: [['Gfg '，7]，['is '，2]，['Best '，4]]，23: [['Gfg '，7]，['is '，2]，['Best '，2]]，24:[' Gfg '，7]，['is '，9]，['Best '

**方法 2:使用积()+循环**

上述功能的组合也可以用来解决这个问题。在本例中，我们使用 product()执行内部和交叉键组合的任务。区别在于分组的容器是元组而不是列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Dictionary Key Value lists combinations
# Using product() + loop
from itertools import product

# initializing dictionary
test_dict = {"Gfg" : [4, 5, 7],
             "is" : [1, 2, 9],
             "Best" : [9, 4, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = {}
for key, val in test_dict.items():

    # for key-value combinations 
    res[key] = product([key], val)

# computing cross key combinations
res = product(*res.values())

# printing result 
print("The computed combinations : " + str(list(res))) 
```

**Output**

> 原始字典为:{'Gfg': [4，5，7]，' is': [1，2，9]，' Best': [9，4，2]}
> 计算出的组合:[(' Gfg '，4)、(' is '，1)、(' Best '，9))、(' Gfg '，4)、(' is '，1)、(' Best '，4))、(' Gfg '，4)、(' is '，1)、(' Best '，2))、((' Gfg '，4)、(' is '，2)、((' 9))、((' Gfg '，5)、(' is '，1)、(' Best '，4))、((' Gfg '，5)、(' is '，1)、(' Best '，2))、(' Gfg '，5)、(' is '，2)、(' Best '，9))、(' Gfg '，5)、(' is '，2)、(' Best '，4)、((' Gfg '，5)、(' is '，2)、(' Best '，2))、((' Gfg '，5)、(' is '，9)、(' Best ' (“is”，2)、(“Best”，2))、((“Gfg”，7)、(“is”，9)、(“Best”，9))、(“Gfg”，7)、(“is”，9)、(“Best”，4))、(“Gfg”，7)、(“is”，9)、(“Best”，2))]