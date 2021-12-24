# Python–在字典中指定反向值

> 原文:[https://www . geesforgeks . org/python-assign-reversed-values-in-dictionary/](https://www.geeksforgeeks.org/python-assign-reversed-values-in-dictionary/)

给定一个字典，在还原字典的值后给每个键赋值。

> **输入** : {1 : 4，2 : 5，3 : 6}
> **输出** : {1 : 6，2 : 5，3 : 4}
> **解释**:数值顺序变了，4，5，6 变 6，5，4。
> 
> **输入** : {1 : 5，2 : 5，3 : 5}
> **输出** : {1 : 5，2 : 5，3 : 5}
> **解释**:数值相同，无可见变化。

**方法#1:使用值()+循环+反向()**

这是执行这项任务的方法之一。在这种情况下，我们使用 reversed()反转字典中的所有值，并重新分配给键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Assign Reversed Values in Dictionary
# Using reversed() + loop + values()

# initializing dictionary
test_dict = {1 : "Gfg", 2 : "is", 3 : "Best"}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# extract values using values()
new_val = list(reversed(list(test_dict.values())))

# reassign new values
res = dict()
cnt = 0
for key in test_dict:
    res[key] = new_val[cnt]
    cnt += 1

# printing result 
print("Reassigned reverse values : " + str(res)) 
```

**Output**

```py
The original dictionary is : {1: 'Gfg', 2: 'is', 3: 'Best'}
Reassigned reverse values : {1: 'Best', 2: 'is', 3: 'Gfg'}

```

**方法 2:使用字典理解+反向()+值()**

上述功能的组合可以用来解决这个问题。在这篇文章中，我们使用字典理解的方法为单行解执行重造反向字典的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Assign Reversed Values in Dictionary
# Using dictionary comprehension + reversed() + values()

# initializing dictionary
test_dict = {1 : "Gfg", 2 : "is", 3 : "Best"}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# extract values using values()
new_val = list(reversed(list(test_dict.values())))

# one-liner dictionary comprehension approach
# enumerate for counter
res = {key : new_val[idx] for idx, key in enumerate(list(test_dict.keys()))}

# printing result 
print("Reassigned reverse values : " + str(res)) 
```

**Output**

```py
The original dictionary is : {1: 'Gfg', 2: 'is', 3: 'Best'}
Reassigned reverse values : {1: 'Best', 2: 'is', 3: 'Gfg'}

```