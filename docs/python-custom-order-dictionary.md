# Python–定制订单字典

> 原文:[https://www . geesforgeks . org/python-custom-order-dictionary/](https://www.geeksforgeeks.org/python-custom-order-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，需要对字典的键进行自定义排序。这是一个相当普遍的问题，随着 Python 较新版本的出现，在字典中对键进行排序，可能需要对字典键进行重新排序。让我们讨论执行这项任务的某些方法。

> **输入**:test _ dict = {“gfg”:1，“is”:2，“best”:3，“for”:4，“极客”:5}
> **输出**:{“gfg”:1，“is”:2，“best”:3，“for”:4，“极客”:5}
> 
> **输入** : test_dict = {“极客”:5、“for”:4、“best”:3、“is”:2、“gfg”:1 }
> **输出**:{“gfg”:1、“is”:2、“best”:3、“for”:4、“极客”:5}

**方法#1:使用循环**
这是蛮力的方式解决这个问题。在这种情况下，我们通过在顺序列表中添加关键字，并与原始字典中的关键字进行映射来构建新字典。与 Python 配合使用> = 3.6。

```py
# Python3 code to demonstrate working of 
# Custom order dictionary
# Using loop

# initializing dictionary
test_dict = {'is' : 2, 'for' : 4, 'gfg' : 1, 'best' : 3, 'geeks' : 5} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing order
ord_list = ['gfg', 'is', 'best', 'for', 'geeks']

# Custom order dictionary
# Using loop
res = dict()
for key in ord_list:
    res[key] = test_dict[key]

# printing result 
print("Ordered dictionary is : " + str(res)) 
```

**Output :**

> 原始字典为:{“is”:2，“for”:4，“gfg”:1，“best”:3，“geeks”:5 }
> 有序字典为:{“gfg”:1，“is”:2，“best”:3，“for”:4，“geeks”:5 }

**方法 2:使用字典理解**
这是执行这项任务的另一种方式。在这种情况下，我们使用速记来使用上述相同的方法解决问题。

```py
# Python3 code to demonstrate working of 
# Custom order dictionary
# Using dictionary comprehension

# initializing dictionary
test_dict = {'is' : 2, 'for' : 4, 'gfg' : 1, 'best' : 3, 'geeks' : 5} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing order
ord_list = ['gfg', 'is', 'best', 'for', 'geeks']

# Custom order dictionary
# Using dictionary comprehension
res = {key : test_dict[key] for key in ord_list}

# printing result 
print("Ordered dictionary is : " + str(res)) 
```

**Output :**

> 原始字典为:{“is”:2，“for”:4，“gfg”:1，“best”:3，“geeks”:5 }
> 有序字典为:{“gfg”:1，“is”:2，“best”:3，“for”:4，“geeks”:5 }