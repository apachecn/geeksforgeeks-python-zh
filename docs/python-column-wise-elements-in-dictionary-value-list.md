# Python–字典值列表中的列式元素

> 原文:[https://www . geesforgeks . org/python-column-wise-elements-in-dictionary-value-list/](https://www.geeksforgeeks.org/python-column-wise-elements-in-dictionary-value-list/)

给定带有值列表的字典，按列提取元素。

> **输入** : test_dict = {'Gfg' : [3，6]，' is' : [4，2]，' best' :[9，1]}
> **输出** : [3，4，9，6，2，1]
> **解释**:从 col1 中提取 3，4，9，然后从 2 中依次提取 6，2，1。
> 
> **输入** : test_dict = {'Gfg' : [3]，' is' : [4]，' best' :[9]}
> **输出**:【3，4，9】
> **解释** : 3，4，9 从 col1 依次开始。

**方法#1:使用生成器表达式+ zip() + *运算符**

在本例中，我们使用 zip()执行提取 columnwise 的任务，并使用*运算符对值进行解包，以便在生成器表达式中进一步展平。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Column-wise elements in Dictionary value list
# Using generator expression + zip() + * operator

# initializing dictionary
test_dict = {'Gfg' : [3, 6, 7],
             'is' : [4, 2, 6], 
             'best' :[9, 1, 3]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# values() gets all values at on
res = list(a for b in zip(*test_dict.values()) for a in b)

# printing result 
print("The extracted values : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': [3, 6, 7], 'is': [4, 2, 6], 'best': [9, 1, 3]}
The extracted values : [3, 4, 9, 6, 2, 1, 7, 6, 3]

```

**方法 2:使用 chain.from_iterable() + zip() + *运算符**

在本例中，展平任务是使用 chain.from_iterable()完成的。其余所有功能与上述方法相似。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Column-wise elements in Dictionary value list
# Using chain.from_iterable() + zip() + * operator
from itertools import chain

# initializing dictionary
test_dict = {'Gfg' : [3, 6, 7],
             'is' : [4, 2, 6], 
             'best' :[9, 1, 3]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# values() gets all values at on
res = list(chain.from_iterable(zip(*test_dict.values())))

# printing result 
print("The extracted values : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': [3, 6, 7], 'is': [4, 2, 6], 'best': [9, 1, 3]}
The extracted values : [3, 4, 9, 6, 2, 1, 7, 6, 3]

```