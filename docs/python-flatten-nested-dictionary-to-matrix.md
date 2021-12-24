# Python–将嵌套字典展平为矩阵

> 原文:[https://www . geesforgeks . org/python-扁平化-嵌套-字典到矩阵/](https://www.geeksforgeeks.org/python-flatten-nested-dictionary-to-matrix/)

有时，在处理数据时，我们会遇到一个问题，即需要将嵌套字典转换为矩阵，每个嵌套由矩阵中的不同行组成。这在许多数据领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `zip() + map()`**
以上功能的组合可以用来执行这个任务。在这种情况下，我们使用蛮力来压平字典键，然后使用 map()和 zip()将它们对齐为矩阵行。

```
# Python3 code to demonstrate working of 
# Flatten Nested Dictionary to Matrix
# using zip() + loop + map()

# initializing dictionary 
test_dict = {'Gfg1' : {'CS':1, 'GATE' : 2}, 
             'Gfg2' : {'CS':2, 'GATE' : 3},
             'Gfg3' : {'CS':4, 'GATE' : 5}} 

# printing original dictionary 
print("The original dictionary is : " + str(test_dict)) 

# Flatten Nested Dictionary to Matrix
# using zip() + loop + map()
temp = list(test_dict.values())
sub = set()
for ele in temp:
    for idx in ele:
        sub.add(idx) 
res = []
res.append(sub)
for key, val in test_dict.items():
    temp2 = []
    for idx in sub:
        temp2.append(val.get(idx, 0))
    res.append(temp2)

res = [[idx for idx, val in test_dict.items()]] + list(map(list, zip(*res)))

# printing result  
print("The Grouped dictionary list is : " + str(res)) 
```

**Output :**

> 原始字典为:{'Gfg3': {'GATE': 5，' CS': 4 '，' Gfg1': {'GATE': 2，' CS': 1}，' Gfg2': {'GATE': 3，' CS': 2}}
> 分组字典列表为:[['Gfg3 '，' Gfg1 '，' Gfg2']，['GATE '，5，2，3]，['CS '，4，1，2]]