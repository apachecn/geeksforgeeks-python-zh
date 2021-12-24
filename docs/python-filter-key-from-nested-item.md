# Python–从嵌套项中过滤关键字

> 原文:[https://www . geesforgeks . org/python-filter-key-from-nested-item/](https://www.geeksforgeeks.org/python-filter-key-from-nested-item/)

有时，在使用 Python 字典时，我们会遇到一个问题，即我们需要提取具有特定键值对的键作为其嵌套项的一部分。这种问题在 web 开发领域很常见。让我们讨论执行这项任务的某些方法。

> **输入**:test _ dict = { ' gfg ':{ ' best ':10，' good' : 5}}
> **输出** : ['gfg']
> 
> **输入**:test _ dict = { ' gfg ':{ ' best ':10，' good' : 12}}
> **输出** : []

**方法#1:使用 loop + `__contains__`**
以上功能的组合构成了执行此任务的蛮力方式。在这种情况下，我们使用循环迭代每个键，并使用 __contains__ 检查值是否存在。

```
# Python3 code to demonstrate working of 
# Filter Key from Nested item
# Using loop + __contains__

# initializing dictionary
test_dict = {'gfg' : {'best' : 4, 'good' : 5}, 
             'is' : {'better' : 6, 'educational' : 4},
             'CS' : {'priceless' : 6}, 
             'Maths' : {'good' : 5}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing dictionary
que_dict = {'good' : 5}

# Filter Key from Nested item
# Using loop + __contains__
res = []
for key, val in test_dict.items():
  if(test_dict[key].__contains__('good')):
    if(test_dict[key]['good'] == que_dict['good']):
        res.append(key)

# printing result 
print("Match keys : " + str(res)) 
```

**Output :**

> 原版词典:{'CS': { '无价':6}，' is': {'better': 6，' educational': 4}，' gfg': {'good': 5，' best': 4}，' mathematics ':{ ' good ':5 } }
> 匹配键:['gfg '，' mathematics ']

**方法 2:使用字典理解+ `get()`**
以上功能的组合提供了解决这个问题的另一种方式。在本文中，我们使用 get()执行元素存在性检查。

```
# Python3 code to demonstrate working of 
# Filter Key from Nested item
# Using dictionary comprehension + get()

# initializing dictionary
test_dict = {'gfg' : {'best' : 4, 'good' : 5}, 
             'is' : {'better' : 6, 'educational' : 4},
             'CS' : {'priceless' : 6}, 
             'Maths' : {'good' : 5}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing dictionary
que_dict = {'good' : 5}

# Filter Key from Nested item
# Using dictionary comprehension + get()
res = [ idx for idx in test_dict if test_dict[idx].get('good') == que_dict['good'] ]

# printing result 
print("Match keys : " + str(res)) 
```

**Output :**

> 原版词典:{'CS': { '无价':6}，' is': {'better': 6，' educational': 4}，' gfg': {'good': 5，' best': 4}，' mathematics ':{ ' good ':5 } }
> 匹配键:['gfg '，' mathematics ']