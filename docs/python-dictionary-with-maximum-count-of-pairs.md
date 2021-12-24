# Python–最大对数字典

> 原文:[https://www . geeksforgeeks . org/python-最多成对计数字典/](https://www.geeksforgeeks.org/python-dictionary-with-maximum-count-of-pairs/)

给定字典列表，提取最大关键字的字典。

> **输入**:test _ list =[{“gfg”:2，“best”:4 }，{“gfg”:2，“is”:3，“best”:4，“CS”:9 }，{“gfg”:2 }]
> **输出** : 4
> **解释**:第二字典最大键数，4。
> 
> **输入**:test _ list =[{“gfg”:2，“best”:4 }，{“gfg”:2 }]
> **输出** : 2
> **解释**:第一字典最大键数，2。

**方法#1:使用 len() + loop**

在这种情况下，我们迭代每个字典，比较每个字典的长度，记录并返回一个最大长度的字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary with maximum keys
# Using loop + len()

# initializing list
test_list = [{"gfg": 2, "best" : 4}, 
             {"gfg": 2, "is" : 3, "best" : 4}, 
             {"gfg": 2}]

# printing original list
print("The original list is : " + str(test_list))

res = {} 
max_len = 0
for ele in test_list:

    # checking for lengths
    if len(ele) > max_len: 
        res = ele
        max_len = len(ele)

# printing results
print("Maximum keys Dictionary : " + str(res))
```

**Output**

```py
The original list is : [{'gfg': 2, 'best': 4}, {'gfg': 2, 'is': 3, 'best': 4}, {'gfg': 2}]
Maximum keys Dictionary : {'gfg': 2, 'is': 3, 'best': 4}

```

**方法 2:使用 max() + key=len**

在这种情况下，我们使用 max()通过传递额外的密钥“len”来计算最大密钥长度，以便根据长度进行比较。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary with maximum keys
# Using max() + key = len

# initializing list
test_list = [{"gfg": 2, "best" : 4}, 
             {"gfg": 2, "is" : 3, "best" : 4}, 
             {"gfg": 2}]

# printing original list
print("The original list is : " + str(test_list))

# maximum length dict using len param
res = max(test_list, key = len)

# printing results
print("Maximum keys Dictionary : " + str(res))
```

**Output**

```py
The original list is : [{'gfg': 2, 'best': 4}, {'gfg': 2, 'is': 3, 'best': 4}, {'gfg': 2}]
Maximum keys Dictionary : {'gfg': 2, 'is': 3, 'best': 4}

```