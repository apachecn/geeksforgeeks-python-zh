# Python–字典值列表中以 K 开头的元素频率

> 原文:[https://www . geesforgeks . org/python-element-frequency-以字典中的 k 开头-value-list/](https://www.geeksforgeeks.org/python-element-frequency-starting-with-k-in-dictionary-value-list/)

有时，在处理大量数据时，我们会遇到一个问题，即我们有字符串列表形式的数据，这些数据是字典关键字的值，我们希望计算以字符 k 开始的元素的出现次数。让我们讨论执行此任务的某些方法。

**方法#1:使用循环+ `startswith()`**
这是可以执行该任务的一种方式。在本文中，我们使用强力嵌套循环检查字典列表中的每个元素，并增加计数器。

```
# Python3 code to demonstrate working of 
# Element Frequency starting with K in dictionary value List
# using loop + startswith()

# initializing dictionary 
test_dict = {1 : ['Gfg', 'is', 'for', 'Geeks'], 2 : ['Gfg', 'is', 'CS', 'God'], 3: ['Gfg', 'best']}

# printing original dictionary 
print("The original dictionary is : " + str(test_dict)) 

# initializing K 
K = 'G'

# Element Frequency starting with K in dictionary value List
# using loop + startswith()
res = 0
for sub in test_dict.values():
    for ele in sub:
           if ele.startswith(K):
                res += 1

# printing result  
print("The element frequency starting with K : " + str(res)) 
```

**Output :**

```
The original dictionary is : {1: ['Gfg', 'is', 'for', 'Geeks'], 2: ['Gfg', 'is', 'CS', 'God'], 3: ['Gfg', 'best']}
The element frequency starting with K : 5

```