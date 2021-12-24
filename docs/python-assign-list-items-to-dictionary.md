# Python–将列表项分配给字典

> 原文:[https://www . geesforgeks . org/python-assign-list-items-to-dictionary/](https://www.geeksforgeeks.org/python-assign-list-items-to-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要在字典中将列表元素指定为新键。此任务可能发生在 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用 zip() + loop**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 zip()将列表元素与字典相结合，并使用循环来结合迭代逻辑。

```py
# Python3 code to demonstrate working of 
# Assign list items to Dictionary
# Using zip() + loop

# initializing list
test_list = [{'Gfg' :  1, 'id' : 2 }, 
             {'Gfg' :  4, 'id' : 4 }]

# printing original list
print("The original list is : " + str(test_list))

# initializing key 
new_key = 'best'

# initializing list 
add_list = [12, 2]

# Assign list items to Dictionary
# Using zip() + loop
res = []
for sub, val in zip(test_list, add_list):
    sub[new_key] = val
    res.append(sub)

# printing result 
print("The modified dictionary : " + str(res)) 
```

**Output :**

> 原始列表为:[{'Gfg': 1，' id': 2}，{'Gfg': 4，' id': 4}]
> 修改后的字典:[{'best': 12，' Gfg': 1，' id': 2}，{'best': 2，' Gfg': 4，' id': 4}]