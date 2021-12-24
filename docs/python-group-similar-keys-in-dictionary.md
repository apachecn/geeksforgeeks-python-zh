# Python–在字典中分组相似的键

> 原文:[https://www . geesforgeks . org/python-group-like-key-in-dictionary/](https://www.geeksforgeeks.org/python-group-similar-keys-in-dictionary/)

有时，在处理字典数据时，我们可能会遇到这样的问题，即我们需要根据关键字的子串进行分组，并对分组在相似关键字上的数据进行重组。这可以在数据预处理中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是我们执行这个任务的野蛮方式。在这种情况下，我们使用条件语句检查元素，并根据子串的存在插入键。

```
# Python3 code to demonstrate working of 
# Group Similar keys in dictionary
# Using loop

# initializing Dictionary
test_dict = {'gfg1' : 1, 'is1' : 2, 'best1' : 3, 
            'gfg2' : 9, 'is2' : 8, 'best2' : 7,
            'gfg3' : 10, 'is3' : 5, 'best3' : 6}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Group Similar keys in dictionary
# Using loop
res = []
res1, res2, res3 = {}, {}, {}
for key, value in test_dict.items():
  if 'gfg' in key:
    res1[key] = value
  elif 'is' in key:
    res2[key] = value
  elif 'best' in key:
    res3[key] = value

res.append(res1)
res.append(res2)
res.append(res3)

# printing result 
print("The grouped similar keys are : " + str(res)) 
```

**Output :**

> 原始字典为:{'best2': 7，' best3': 6，' is2': 8，' is3': 5，' best1': 3，' gfg1': 1，' gfg3': 10，' is1': 2，' gfg2': 9}
> 分组的相似键为:[{'gfg3': 10，' gfg2': 9，' gfg1': 1}，{'is2': 8，' is3': 5，' is1': 2}，{'best3': 6，' best1': 3，' best2': 7}]