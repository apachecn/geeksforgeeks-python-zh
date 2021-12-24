# Python–替代默认键值

> 原文:[https://www . geesforgeks . org/python-alternate-default-key-value/](https://www.geeksforgeeks.org/python-alternate-default-key-value/)

有时，在使用 Python Dictionaries 时，我们可能会遇到这样的问题:我们需要为特定的键分配特定的值，但是在没有的情况下，需要相似的键的值，但是来自不同的字典。这个问题可以在 web 开发领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'gfg' : {'a' : 1，' b' : 2，' c' : 3}，' best' : {'a' : 3，' c' : 4，' b' : 17}}
> **输出** : 17
> 
> **输入** : test_dict = {'gfg' : {'b' : 1}，' best' : {'a' : 3}}
> **输出** : 1

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们测试特定字典的值，如果不存在，我们检查替代键并赋值。

```
# Python3 code to demonstrate working of 
# Alternate Default Key Value
# Using loop

# initializing dictionary
test_dict = {'gfg' : {'a' : 1, 'b' : 2, 'c' : 3}, 'best' : {'a' : 3, 'c' : 4}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# alternate key 
alt_key = 'gfg'

# Alternate Default Key Value
# Using loop
if 'b' in test_dict['best']:
    res = test_dict['best']['b']
else :
    res = test_dict[alt_key]['b']

# printing result 
print("The required value : " + str(res)) 
```

**Output :**

> 原始字典为:{'gfg': {'a': 1，' b': 2，' c': 3}，' best': {'a': 3，' c': 4}}
> 所需值:2

**方法 2:使用 `get()`**
这个任务也可以使用这个方法来执行。我们可以利用 get()的功能在缺少值的情况下呈现默认值。

```
# Python3 code to demonstrate working of 
# Alternate Default Key Value
# Using get()

# initializing dictionary
test_dict = {'gfg' : {'a' : 1, 'b' : 2, 'c' : 3}, 'best' : {'a' : 3, 'c' : 4}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# alternate key 
alt_key = 'gfg'

# Alternate Default Key Value
# Using get()
res = test_dict.get('best').get('b', test_dict.get(alt_key)['b'])

# printing result 
print("The required value : " + str(res)) 
```

**Output :**

> 原始字典为:{'gfg': {'a': 1，' b': 2，' c': 3}，' best': {'a': 3，' c': 4}}
> 所需值:2