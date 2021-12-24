# Python–构建由分隔符分隔的字典键值对

> 原文:[https://www . geesforgeks . org/python-construct-dictionary-key-value-pairs-由分隔符分隔/](https://www.geeksforgeeks.org/python-construct-dictionary-key-value-pairs-separated-by-delimiter/)

给定一个键值对由 delim 分隔的字符串，构造一个字典。

> **输入** : test_str = 'gfg#3，is#9，best#10 '，delim = '#'
> **输出** : {'gfg': '3 '，' is': '9 '，' best': '10'}
> **解释** : gfg 与 3 配对，如同与# delim 分开。
> **输入** : test_str = 'gfg.10 '，delim = ' '
> **输出** : {'gfg': '10'}
> **解释** : gfg 与 10 配对，如与分开。德利姆。

**方法#1:使用 split() +循环**

在本例中，我们对逗号执行拆分，以获得键值对，并对自定义 delim 再次执行拆分，以获得分开的键值对。然后使用循环分配给字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Contruct dictionary Key-Value pairs separated by delim
# Using split() + loop

# initializing strings
test_str = 'gfg$3, is$9, best$10'

# printing original string
print("The original string is : " + str(test_str))

# initializing delim
delim = "{content}quot;

# split by comma for getting different dict values
dicts = test_str.split(', ')

res = dict()
for sub in dicts:

    # 2nd split for forming Key-Values for dictionary
    res[sub.split(delim)[0]]  = sub.split(delim)[1]

# printing result
print("The constructed dictionary : " + str(res))
```

**Output**

```
The original string is : gfg$3, is$9, best$10
The constructed dictionary : {'gfg': '3', 'is': '9', 'best': '10'}
```

**方法 2:使用词典理解+拆分()**

与上述方法类似，不同之处在于词典理解用于执行词典构建任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Contruct dictionary Key-Value pairs separated by delim
# Using split() + dictionary comprehension

# initializing strings
test_str = 'gfg$3, is$9, best$10'

# printing original string
print("The original string is : " + str(test_str))

# initializing delim
delim = "{content}quot;

# split by comma for getting different dict values
dicts = test_str.split(', ')

# dictionary comprehension to form dictionary
res = {sub.split(delim)[0] : sub.split(delim)[1] for sub in dicts}

# printing result
print("The constructed dictionary : " + str(res))
```

**Output**

```
The original string is : gfg$3, is$9, best$10
The constructed dictionary : {'gfg': '3', 'is': '9', 'best': '10'}
```