# Python–按字母顺序提取连续字母的字符串

> 原文:[https://www . geesforgeks . org/python-extract-string-with-sequence-alphabet-order/](https://www.geeksforgeeks.org/python-extract-strings-with-successive-alphabets-in-alphabetical-order/)

给定一个字符串列表，提取按字母顺序连续出现的字符列表。

> **输入** : test_list = ['gfg '，' ij '，' best '，' for '，' geeks']
> **输出** : ['ij '，' gfg '，' best']
> **解释** : i-j，f-g，s-t 为连续对。
> 
> **输入** : test_list = ['gf1g '，' in '，' besht '，' for '，' geeks']
> **输出** : []
> **解释**:无连续对。

**方法#1:使用 order()+循环**

在本例中，我们检查每个字符串是否包含前面字符的字母后继字符，ASCII 转换使用 order()完成。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Strings with successive Alphabets
# Using ord() + loop

# initializing string list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:

    # iterating for string 
    for idx in range(len(sub) - 1):

        # checking for alphabetic consecution
        if ord(sub[idx]) == ord(sub[idx + 1]) - 1:
            res.append(sub)
            break

# printing result 
print("Strings with alphabetic consecution : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Strings with alphabetic consecution : ['gfg', 'best']

```

**方法 2:使用任意()+滤波器()+λ**

在这种情况下，我们使用 any()检查任何继承，过滤任务使用 filter()和 lambda 函数完成。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Strings with successive Alphabets
# Using any() + filter() + lambda

# initializing string list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# filtering using filter, and checking for any substring using any()
res = list(filter(lambda sub: any(ord(sub[idx]) == ord(
    sub[idx + 1]) - 1 for idx in range(len(sub) - 1)), test_list))

# printing result
print("Strings with alphabetic consecution : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Strings with alphabetic consecution : ['gfg', 'best']

```