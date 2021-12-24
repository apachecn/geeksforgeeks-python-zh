# Python–提取特定值类型的键

> 原文:[https://www . geesforgeks . org/python-extract-key-with-specific-value-type/](https://www.geeksforgeeks.org/python-extract-keys-with-specific-value-type/)

给定一个字典，提取所有键值都是给定类型的。

> **输入** : test_dict = {'gfg' : 2，' is' : 'hello '，' for' : {'1' : 3}，' geeks' : 4}，targ_type = int
> **输出** : ['gfg '，' geeks']
> **解释** : gfg 和 geeks 有整数值。
> 
> **输入** : test_dict = {'gfg' : 2，' is' : 'hello '，' for' : {'1' : 3}，' geeks' : 4}，targ_type = str
> **输出** : ['is']
> **解释** : is 有字符串值。

**方法#1:使用 loop+**[**is instance()**](https://www.geeksforgeeks.org/python-isinstance-method/)

**在本例中，我们使用 *isinstance()* 检查数据类型，并使用循环迭代所有值。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of
# Extract Keys with specific Value Type
# Using loop + isinstance()

# initializing dictionary
test_dict = {'gfg': 2, 'is': 'hello', 'best': 2, 'for': {'1': 3}, 'geeks': 4}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing type
targ_type = int

res = []
for key, val in test_dict.items():

    # checking for values datatype
    if isinstance(val, targ_type):
        res.append(key)

# printing result
print("The extracted keys : " + str(res))
```

****输出:****

> **原始字典为:{'gfg': 2，' is': 'hello '，' best': 2，' for': {'1': 3}，' geeks': 4}
> 提取的键:['gfg '，' best '，' geeks']**

****方法 2:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[**is instance()**](https://www.geeksforgeeks.org/python-isinstance-method/)**

**与上述方法类似，单行速记使用列表理解来解决这个问题。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of
# Extract Keys with specific Value Type
# Using list comprehension + isinstance()

# initializing dictionary
test_dict = {'gfg': 2, 'is': 'hello', 'best': 2, 'for': {'1': 3}, 'geeks': 4}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing type
targ_type = int

# one-liner to solve the problem
res = [key for key, val in test_dict.items() if isinstance(val, targ_type)]

# printing result
print("The extracted keys : " + str(res))
```

****输出:****

> **原始字典为:{'gfg': 2，' is': 'hello '，' best': 2，' for': {'1': 3}，' geeks': 4}
> 提取的键:['gfg '，' best '，' geeks']**