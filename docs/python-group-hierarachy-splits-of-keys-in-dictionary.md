# Python–字典中键的组层次拆分

> 原文:[https://www . geesforgeks . org/python-group-hierarchy-splits-of-key-in-dictionary/](https://www.geeksforgeeks.org/python-group-hierarachy-splits-of-keys-in-dictionary/)

给定一个带有由拆分字符连接的键的字典，任务是编写一个 Python 程序，将字典变成嵌套和分组字典。

**示例**

> **输入:** test_dict = {"1-3" : 2，" 1-8" : 10}，splt_chr = "-"
> 
> **输出:** {'1': {'3': 2，' 8': 10}}
> 
> **说明:** 1 链接到值为 2 的 3 和值为 10 的 8，因此这些元素被嵌套并赋值。
> 
> **输入:**test _ dict = {“1-3”:2、“8-7”:0、“1-8”:10、“8-6”:15 }，splt _ chr =“-”
> 
> **输出:** {'1': {'3': 2，' 8': 10}，' 8': {'7': 0，' 6': 15}}
> 
> **解释:** 1 链接到值为 2 的 3，值为 10 的 8，类似地，值为 0 的 8 链接到值为 0 的 7，值为 15 的 6，因此这些元素是嵌套的，并且赋值。

### **方法#1:使用 loop+**[**split()**](https://www.geeksforgeeks.org/python-string-split/)

在本例中，我们使用 split()执行拆分键进行展平的任务。然后使用字典来完成键的记忆，该字典将找到的其他类似的嵌套键添加到其嵌套字典中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Group Hierarachy Splits of keys in Dictionary
# Using loop + split()

# initializing dictionary
test_dict = {"1-3" : 2, "8-7" : 0, "1-8" : 10, "8-6" : 15}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing split char 
splt_chr = "-"

res = dict()
for key, val in test_dict.items():
    ini_key, low_key = key.split(splt_chr)

    # check if key already present
    if ini_key not in res:
        res[ini_key] = dict()

    # add nested value if present key
    res[ini_key][low_key] = val

# printing result
print("The splitted dictionary : " + str(res))
```

**Output**

```py
The original dictionary is : {'1-3': 2, '8-7': 0, '1-8': 10, '8-6': 15}
The splitted dictionary : {'1': {'3': 2, '8': 10}, '8': {'7': 0, '6': 15}}
```

### **方法 2:使用**[**default dict()**](https://www.geeksforgeeks.org/defaultdict-in-python/)

与上述方法类似，唯一的区别是 defaultdict()用于记忆分组键的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Group Hierarachy Splits of keys in Dictionary
# Using defaultdict() 
from collections import defaultdict

# initializing dictionary
test_dict = {"1-3" : 2, "8-7" : 0, "1-8" : 10, "8-6" : 15}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing split char 
splt_chr = "-"

res = defaultdict(dict)
for key, val in test_dict.items():
    ini_key, low_key = key.split(splt_chr)

    # defaultdict eliminates check step
    res[ini_key][low_key] = val

# printing result
print("The splitted dictionary : " + str(dict(res)))
```

**Output**

```py
The original dictionary is : {'1-3': 2, '8-7': 0, '1-8': 10, '8-6': 15}
The splitted dictionary : {'1': {'3': 2, '8': 10}, '8': {'7': 0, '6': 15}}
```