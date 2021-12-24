# Python–字典值映射求和

> 原文:[https://www . geesforgeks . org/python-dictionary-values-mapped-summary/](https://www.geeksforgeeks.org/python-dictionary-values-mapped-summation/)

给定一个带有值列表的字典，我们的任务是提取使用映射找到的值的总和。

> **输入:** test_dict = {4 : ['a '，' v '，' b '，' e']，
> 
> 1 : ['g '，' f '，' g']，
> 
> 3:“e”、“v”文件夹、文件夹 _ false =“a:3”、“g:8”、“f:10”、“b:4”、“e:7”、“v:2”
> 
> **输出:** {4: 16，1: 26，3: 9}
> 
> **说明:**“g”有 8，“f”有 10 作为量值，因此 1 由 8 + 8 + 10 = 26 映射。(映射列表的总和)。
> 
> **输入:** test_dict = {4 : ['a '，' v '，' b '，' e']，
> 
> 1:[' g '、' f '、' g ']}、map _ vals = { ' a ':' 3 '、' g '、` 8 '、` f '、` 10 '、` b '、` 4 '、` e '、` 7 '、` v '、` 2}
> 
> **输出:** {4: 16，1: 26}
> 
> **说明:**“g”有 8，“f”有 10 作为量值，因此 1 由 8 + 8 + 10 = 26 映射。(映射列表的总和)。

**方法一:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+** [**项()**](https://www.geeksforgeeks.org/python-dictionary-items-method/)

在这种情况下，每个关键字在字典和每个字典的每个值中迭代。使用已初始化的映射和字典进行迭代和求和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Dictionary Values Mapped Summation
# Using loop + items()

# initializing dictionary
test_dict = {4 : ['a', 'v', 'b', 'e'],
             1 : ['g', 'f', 'g'],
             3 : ['e', 'v']}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# values mapped 
map_vals = {'a' : 3, 'g' : 8, 'f' : 10,
            'b' : 4, 'e' : 7, 'v' : 2}

res = dict()
# items() getting keys and values
for key, vals in test_dict.items():
    sum = 0
    for val in vals:

        # summing with mappings
        sum += map_vals[val]
    res[key] = sum

# printing result
print("The extracted values sum : " + str(res))
```

**输出:**

> 原始字典为:{4: ['a '，' v '，' b '，' e']，1: ['g '，' f '，' g']，3: ['e '，' v']}
> 
> 提取的值总和:{4: 16，1: 26，3: 9}

**方法二:使用** [**字典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/) **+** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/)

在本例中，我们使用 sum()执行获取每个值的和的任务。字典理解用于获取关键字，并以速记方式将相应的值赋给 sum。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Dictionary Values Mapped Summation
# Using dictionary comprehension + sum()

# initializing dictionary
test_dict = {4 : ['a', 'v', 'b', 'e'],
             1 : ['g', 'f', 'g'],
             3 : ['e', 'v']}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# values mapped 
map_vals = {'a' : 3, 'g' : 8, 'f' : 10,
            'b' : 4, 'e' : 7, 'v' : 2}

# sum() gets sum of each mapped values 
res = {key : sum(map_vals[val] for val in vals) 
       for key, vals in test_dict.items()}

# printing result
print("The extracted values sum : " + str(res))
```

**输出:**

> 原始字典为:{4: ['a '，' v '，' b '，' e']，1: ['g '，' f '，' g']，3: ['e '，' v']}
> 
> 提取的值总和:{4: 16，1: 26，3: 9}