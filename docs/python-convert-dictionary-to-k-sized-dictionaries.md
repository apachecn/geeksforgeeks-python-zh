# Python–将字典转换为 K 大小的字典

> 原文:[https://www . geesforgeks . org/python-convert-dictionary-to-k-size-dictionary/](https://www.geeksforgeeks.org/python-convert-dictionary-to-k-sized-dictionaries/)

给定一个字典，将字典分成 K 个不同大小的字典列表。

> **输入** : test_dict = {'Gfg' : 1，' is' : 2，' best' : 3，' for' : 4，' geeks' : 5，' CS' : 6}，K = 3
> **输出** : [{'Gfg': 1，' is': 2，' best': 3}，{'for': 4，' geeks': 5，' CS': 6}]
> **解释**:分为大小 3 个键。
> 
> **输入** : test_dict = {'Gfg' : 1，' is' : 2，' best' : 3，' for' : 4}，K = 2
> **输出** : [{'Gfg': 1，' is': 2}，{'best': 3，' for': 4}]
> **解释**:分为大小 2 个键。

**方法:使用循环**

在这种情况下，我们使用循环迭代字典中的所有键，并根据大小进行分叉，然后添加到新列表中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert dictionary to K Keys dictionaries
# Using loop

# initializing dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 4, 'geeks' : 5, 'CS' : 6}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 2

res = []
count = 0
flag = 0
indict = dict()
for key in test_dict:
    indict[key] = test_dict[key]        
    count += 1

    # checking for K size and avoiding empty dict using flag
    if count % K == 0 and flag:
        res.append(indict)

        # reinitializing dictionary
        indict = dict()
        count = 0
    flag = 1

# printing result 
print("The converted list : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 1, 'is': 2, 'best': 3, 'for': 4, 'geeks': 5, 'CS': 6}
The converted list : [{'Gfg': 1, 'is': 2}, {'best': 3, 'for': 4}, {'geeks': 5, 'CS': 6}]

```