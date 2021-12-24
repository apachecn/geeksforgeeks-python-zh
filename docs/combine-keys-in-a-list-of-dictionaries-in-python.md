# 在 Python 的字典列表中组合关键字

> 原文:[https://www . geeksforgeeks . org/python 字典列表中的组合键/](https://www.geeksforgeeks.org/combine-keys-in-a-list-of-dictionaries-in-python/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要在具有相似键的列表中执行字典合并。这种问题可能出现在数据优化领域。让我们讨论一下执行这项任务的方法。

> **输入** : test_list = [{'a': 6}、{'b': 2}、{'a': 9}、{'b': 7}]
> **输出** : [{'b': 2、' a': 6}、{'b': 7、' a': 9}]
> 
> **输入** : test_list = [{'a': 8}，{'a': 2}，{'a': 3}]
> **输出** : [{'a': 8}，{'a': 2}，{'a': 3}]

**方法:loop + `**`运算符**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用蛮力来构建一个新的字典，并且只有在当前字典中没有添加关键字的情况下才添加关键字。合并字典的任务是使用“**”运算符对初始字典进行解包，然后使用通常的字典初始化构造{}用没有重复键和新键的字典再次打包。

```
# Python3 code to demonstrate working of 
# Merge Similar Dictionaries in List
# Using loop + "**" operator

# initializing list
test_list = [{'gfg' : 1}, {'is' : 2}, {'best' : 3},
              {'gfg' : 5}, {'is' : 17}, {'best' : 14},
              {'gfg' : 7}, {'is' : 8}, {'best' : 10},]

# printing original list
print("The original list is : " + str(test_list))

# Merge Similar Dictionaries in List
# Using loop + "**" operator
res = [{}]
for sub in test_list:
    if list(sub)[0] not in res[-1]:
        res[-1] = {**res[-1], **sub}
    else:
        res.append(sub)

# printing result 
print("The merged dictionaries : " + str(res)) 
```

**Output :**

> 原始列表为:[{'gfg': 1}、{'is': 2}、{'best': 3}、{'gfg': 5}、{'is': 17}、{'best': 14}、{'gfg': 7}、{'is': 8}、{'best': 10}]
> 合并后的词典:[{'best': 3，' is': 2，' gfg': 1}、{'best': 14，' is': 17，' gfg': 5}、{'best': 10，' is': 1