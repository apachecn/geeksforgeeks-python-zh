# Python–提取总和大于 K 的字典项目

> 原文:[https://www . geesforgeks . org/python-extract-dictionary-items-with-summary-大于-k/](https://www.geeksforgeeks.org/python-extract-dictionary-items-with-summation-greater-than-k/)

给定带有值列表的字典，提取所有那些值加起来超过 k 的项目

> **输入**:{“Gfg”:[6，3，4]，“is”:[8，10，12]，“Best”:[10，16，14]，“for”:[7，4，3]，“极客”:[1，2，3，4]}，K = 10
> **输出**:{“Gfg”:[6，3，4]，“is”:[8，10，12]，“Best”:[10，16
> 
> **输入**:{“Gfg”:[6，3，4]，“is”:[8，10，12]，“Best”:[10，16，14]，“for”:[7，4，3]，“极客”:[1，2，3，4]}，K = 50
> **输出** : {}
> **解释**:没有大于 50 的元素。

**方法一:使用词典理解+求和()**

这是解决这个问题的方法之一。在这个单行代码中，只有当字典项的值的总和与使用 sum()计算的 K 交叉时，我们才迭代关键字并追加字典项。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Dictionary Items with Summation Greater than K
# Using dictionary comprehension + sum()

# initializing dictionary
test_dict = {"Gfg" : [6, 3, 4], 
             "is" :  [8, 10, 12], 
             "Best" : [10, 16, 14],  
             "for" : [7, 4, 3], 
             "geeks" : [1, 2, 3, 4]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 15

# summation using sum(), values extracted using items()
res = {key: val for key, val in test_dict.items() if sum(val) > K}

# printing result 
print("The computed dictionary : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': [6, 3, 4], 'is': [8, 10, 12], 'Best': [10, 16, 14], 'for': [7, 4, 3], 'geeks': [1, 2, 3, 4]}
The computed dictionary : {'is': [8, 10, 12], 'Best': [10, 16, 14]}

```

**方法 2:使用 filter()+lambda()+sum()+dict()**

这是执行该任务的另一种方式。在这种情况下，计算部分使用 filter()和 lambda 完成，使用 sum()进行求和，使用 dict()将结果转换为字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Dictionary Items with Summation Greater than K
# Using filter() + lambda() + sum() + dict()

# initializing dictionary
test_dict = {"Gfg" : [6, 3, 4], 
             "is" :  [8, 10, 12], 
             "Best" : [10, 16, 14],  
             "for" : [7, 4, 3], 
             "geeks" : [1, 2, 3, 4]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 15

# summation using sum(), values extracted using items()
# filter() + lambda used for computation
res = dict(filter(lambda ele: sum(ele[1]) > K, test_dict.items()))

# printing result 
print("The computed dictionary : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': [6, 3, 4], 'is': [8, 10, 12], 'Best': [10, 16, 14], 'for': [7, 4, 3], 'geeks': [1, 2, 3, 4]}
The computed dictionary : {'is': [8, 10, 12], 'Best': [10, 16, 14]}

```