# Python–在字典中给定关键字后添加项目

> 原文:[https://www . geesforgeks . org/python-字典中给定关键字后添加项目/](https://www.geeksforgeeks.org/python-add-item-after-given-key-in-dictionary/)

给定一个字典和一个关键字，在字典中的某个关键字后添加新项。

> **输入**:test _ dict = {“Gfg”:3、“is”:5、“for”:8、“Geeks”:10 }、K =“is”，add _ Item = {“good”:19 }
> **输出**:{“Gfg”:3、“is”:5、“good”:19、“for”:8、“Geeks”:10 }
> **解释**:字典中所需键后添加的项。
> 
> **输入**:test _ dict = {“Gfg”:3、“is”:5、“for”:8、“极客”:10}、K =“for”，add _ Item = {“good”:19 }
> **输出**:{“Gfg”:3、“is”:5、“for”:8、“good”:19、“极客”:10}
> **解释**:字典中所需键后添加的项。

**方法:使用循环+更新()**

在这种情况下，我们对所有的键进行迭代，当遇到目标键时，迭代被传送，字典用所需的键更新。然后迭代恢复。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Dictionary Keys whose Values summation equals K 
# Using loop + update()

# initializing dictionary
test_dict = {"Gfg" : 3, "is" : 5, "for" : 8, "Geeks" : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = "is"

# initializing dictionary to be added 
add_item = {"best" : 19}

# using dictionary comprehension 
res = dict()
for key in test_dict:
    res[key] = test_dict[key]

    # modify after adding K key
    if key == K:
        res.update(add_item)

# printing result 
print("Modified dictionary : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': 3, 'is': 5, 'for': 8, 'Geeks': 10}
Modified dictionary : {'Gfg': 3, 'is': 5, 'best': 19, 'for': 8, 'Geeks': 10}

```