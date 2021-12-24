# Python–连接字典列表中的字符串值

> 原文:[https://www . geesforgeks . org/python-concatenate-string-values-in-dictionary-list/](https://www.geeksforgeeks.org/python-concatenate-string-values-in-dictionary-list/)

有时，在使用 Python 记录数据时，我们可能会遇到一个问题，即我们需要通过匹配特定的键(如标识)来执行键的字符串值的串联。这类问题在 web 开发领域会有应用。让我们讨论一下执行这项任务的具体方法。

> **输入** : test_list = [{'id': 17，' gfg': 'geeksfor'}，{'id': 12，' gfg': 'geeks'}，{'id': 34，' gfg': 'good'}]
> **输出** : [{'id': 17，' gfg': 'geeksfor'}，{'id': 12，' gfg': 'geeks'}，{'id': 34，' gfg': 'good'}]
> 
> 输入:test _ list =[{‘id:’1、’gfg:‘geeks for’}，{‘id:’1、’gfg:’geeks’}，{‘id:’1、‘gfg:’good’]
> **输出**:[{‘id:’1、’gfg:’geeksforgeeksgood’}]

**方法#1:使用循环**
这是解决这个问题的一种方法。在这种情况下，我们检查每个键，然后在相等键的基础上执行合并，并在强力方法中执行特定所需键的连接。

```
# Python3 code to demonstrate working of 
# Concatenate String values in Dictionary List
# Using loop

# initializing list
test_list = [{'gfg' : "geeksfor", 'id' : 12, 'best' : (1, 2)}, 
            {'gfg' : "geeks", 'id' : 12, 'best' : (6, 2)},
            {'gfg' : "good", 'id' : 34, 'best' : (7, 2)}]

# printing original list
print("The original list is : " + str(test_list))

# initializing compare key 
comp_key = 'id'

# initializing concat key 
conc_key = 'gfg'

# Concatenate String values in Dictionary List
# Using loop
res = []
for ele in test_list:
    temp = False
    for ele1 in res:
        if ele1[comp_key] == ele[comp_key]:
             ele1[conc_key] = ele1[conc_key] +  ele[conc_key]
             temp = True
             break
    if not temp:
         res.append(ele)

# printing result 
print("The converted Dictionary list : " + str(res)) 
```

**Output :**

> 原始字典:{'gfg': {'is': [6，7，8]，' best': [1，9，4]}}
> 
> 可能的组合有:{'gfg5': {'is': 7，' best': 4}，' gfg3': {'is': 7，' best': 1}，' gfg8': {'is': 8，' best': 4}，' gfg2': {'is': 6，' best': 4}，' gfg6': {'is': 8，' best': 1}，' gfg0': {'is': 6，' best': 9}，' gfg7 ':