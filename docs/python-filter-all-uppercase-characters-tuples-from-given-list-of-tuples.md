# Python–从给定的元组列表中过滤所有大写字符元组

> 原文:[https://www . geesforgeks . org/python-filter-全大写字符-元组-来自给定元组列表/](https://www.geeksforgeeks.org/python-filter-all-uppercase-characters-tuples-from-given-list-of-tuples/)

给定元组列表，过滤包含所有大写字符的元组。

> **输入**:test _ list =[(' GFG '，' IS '，' BEST ')，(' GFG '，' AVERAGE ')，(' GFg '，' CS ')]
> **输出** : [('GFG '，' IS '，' BEST')]
> **解释**:只有 1 个元组全大写字符串。
> 
> **输入**:test _ list =[(“GFG”、“iS”、“BEST”)、(“GFG”、“AVERAGE”)、(“GFg”、“CS”)]
> **输出** : []
> **解释** : No 有全大写的 Strings。

**方法#1:使用循环**

在这种情况下，我们对每个元组进行迭代，并检查每个字符串是否都是大写的，如果不是，则从新的元组中省略该元组。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Filter uppercase characters Tuples
# Using loop

# initializing list
test_list = [("GFG", "IS", "BEST"), ("GFg", "AVERAGE"), ("GFG", ), ("Gfg", "CS")]

# printing original list
print("The original list is : " + str(test_list))

res_list = []
for sub in test_list:
    res = True 
    for ele in sub:

        # checking for uppercase
        if not ele.isupper():
            res = False 
            break
    if res:
        res_list.append(sub)

# printing results
print("Filtered Tuples : " + str(res_list))
```

**Output**

```py
The original list is : [('GFG', 'IS', 'BEST'), ('GFg', 'AVERAGE'), ('GFG', ), ('Gfg', 'CS')]
Filtered Tuples : [('GFG', 'IS', 'BEST'), ('GFG', )]

```

**方法 2:使用列表理解+ all() + isupper()**

在本文中，我们使用 all()检查所有大写字符串，列表理解提供了问题的紧凑解决方案。isupper()用于检查大写字母。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Filter uppercase characters Tuples
# Using list comprehension + all() + isupper()

# initializing list
test_list = [("GFG", "IS", "BEST"), ("GFg", "AVERAGE"), ("GFG", ), ("Gfg", "CS")]

# printing original list
print("The original list is : " + str(test_list))

# all() returns true only when all strings are uppercase
res = [sub for sub in test_list if all(ele.isupper() for ele in sub)]

# printing results
print("Filtered Tuples : " + str(res))
```

**Output**

```py
The original list is : [('GFG', 'IS', 'BEST'), ('GFg', 'AVERAGE'), ('GFG', ), ('Gfg', 'CS')]
Filtered Tuples : [('GFG', 'IS', 'BEST'), ('GFG', )]

```