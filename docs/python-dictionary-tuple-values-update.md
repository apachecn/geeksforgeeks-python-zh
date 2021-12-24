# Python–字典元组值更新

> 原文:[https://www . geesforgeks . org/python-dictionary-tuple-values-update/](https://www.geeksforgeeks.org/python-dictionary-tuple-values-update/)

有时候，在处理元组数据时，我们在执行它的版本时会遇到问题，原因是它的不变性。本文讨论字典中元组值的版本。这在许多领域都有应用，因为字典通常是网络开发和数据科学领域中流行的数据类型。让我们讨论一下解决这个问题的某些方法。

> **输入** :
> test_dict = {'Gfg' : (5，6，7，8)}
> K = 2
> T5】输出 : {'Gfg': (10，12，14，16)}
> 
> **输入** :
> test_dict = {'Gfg' : (5，，，' is' : (6)，，' best' : (7，}
> K = 7
> **输出** : {'Gfg': (35，，，' is': (42，，' best': (49，}

**方法#1:使用生成器表达式+字典理解**
上述功能的组合提供了一种线性蛮力方法来解决这个问题。在这种情况下，我们使用生成器表达式和字典理解来执行编辑任务，以用编辑后的值来重新构建字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Dictionary Tuple values update
# Using generator expression + dictionary comprehension

# initializing dictionary
test_dict = {'Gfg' : (5, 6), 'is' : (7, 8), 'best' : (10, 11)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
# performing multiplication by K
K = 3

# Dictionary Tuple values update
# Using generator expression + dictionary comprehension
res = {key: tuple(idx * K for idx in val)
          for key, val in test_dict.items()}

# printing result
print("The edited tuple values : " + str(res))
```

**Output : **

```py
The original dictionary is : {'Gfg': (5, 6), 'is': (7, 8), 'best': (10, 11)}
The edited tuple values : {'Gfg': (15, 18), 'is': (21, 24), 'best': (30, 33)}
```

**方法 2:使用 map() + lambda() + dict()**
上述功能的组合也提供了解决这个问题的方法。在这种情况下，使用 lambda()赋值，使用 dict()构造字典。将逻辑扩展到每个键的任务是使用 map()完成的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Dictionary Tuple values update
# Using map() + lambda() + dict()

# initializing dictionary
test_dict = {'Gfg' : (5, 6), 'is' : (7, 8), 'best' : (10, 11)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
# performing multiplication by K
K = 3

# Dictionary Tuple values update
# Using map() + lambda() + dict()
res = dict(map(lambda sub: (sub[0], (sub[1][0] * K,
               sub[1][1] * K)), test_dict.items()))

# printing result
print("The edited tuple values : " + str(res))
```

**Output : **

```py
The original dictionary is : {'Gfg': (5, 6), 'is': (7, 8), 'best': (10, 11)}
The edited tuple values : {'Gfg': (15, 18), 'is': (21, 24), 'best': (30, 33)}
```