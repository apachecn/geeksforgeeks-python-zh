# Python–提取 K 键值的元素

> 原文:[https://www . geeksforgeeks . org/python-extract-ith-element-of-k-keys-value/](https://www.geeksforgeeks.org/python-extract-ith-element-of-k-keys-value/)

给定一个字典，提取 K 键值列表中的元素。

> **输入** : test_dict = {'Gfg' : [6，7，3，1]，' is' : [9，1，4]，' best' : [10，7，4]}，K = 'Gfg '，i = 1
> **输出** : 7
> **解释**:第一个指标的' Gfg ' s 值为 7。
> 
> **输入** : test_dict = {'Gfg' : [6，7，3，1]，' is' : [9，1，4]，' best' : [10，7，4]}，K = 'best '，i = 0
> **输出** : 10
> **解释**:第 0 个指标的' best ' s 值为 10。

**方法:使用+ get()**

这是执行这项任务的方法之一。在这种情况下，我们使用 get()提取密钥的值，然后在检查 K 是否小于列表长度后提取值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract ith element of K key's value
# Using get()

# initializing dictionary
test_dict = {'Gfg' : [6, 7, 3, 1],
             'is' : [9, 1, 4],
             'best' : [10, 7, 4]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
K = 'Gfg'

# initializing i
i = 2

# using get() to get the required value
temp = test_dict.get(K)
res = None
# checking for non empty dict and length constraints
if temp and len(temp) >= i:  
        res = temp[i]

# printing result
print("The extracted value : " + str(res))
```

**Output**

```py
The original dictionary is : {'Gfg': [6, 7, 3, 1], 'is': [9, 1, 4], 'best': [10, 7, 4]}
The extracted value : 3
```