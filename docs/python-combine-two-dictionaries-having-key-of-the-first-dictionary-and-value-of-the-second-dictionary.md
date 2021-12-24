# Python–合并两个字典，第一个字典的关键字和第二个字典的值

> 原文:[https://www . geesforgeks . org/python-combine-two-dictionary-first-dictionary-key-of-second-dictionary/](https://www.geeksforgeeks.org/python-combine-two-dictionaries-having-key-of-the-first-dictionary-and-value-of-the-second-dictionary/)

给了两本字典。任务是以这样一种方式合并它们，即结果字典包含第一个字典中的键和第二个字典中的值。

**示例:**

> **输入**:test _ dict 1 = {“Gfg”:20、“is”:36、“best”:100 }、test _ dict 2 = {“Gfg 2”:26、“is2”:20、“best 2”:70 }
> **输出**:{“Gfg”:26、“is”:20、“best”:70 }
> **解释**:类似索引键的值赋给字典 1。
> 
> **输入**:test _ dict 1 = {“Gfg”:20，【最佳】:100}，test _ dict 2 = {“Gfg 2”:26，【最佳 2】:70 }
> **输出**:{“Gfg”:26，【最佳】:70}
> **解释**:类似索引键的值赋给字典 1。

**方法#1:使用循环+按键()**

这是执行这项任务的一种方式。在这种情况下，我们使用 key()提取所有的键，然后在循环内部分配所需的值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Assign similar index values in Dictionary
# Using loop + keys()

# initializing dictionaries
test_dict1 = {"Gfg" : 20, "is" : 36, "best" : 100}
test_dict2 = {"Gfg2" : 26, "is2" : 19, "best2" : 70}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# extracting keys and values
keys1 = list(test_dict1.keys())
vals2 = list(test_dict2.values())

# assigning new values 
res = dict()
for idx in range(len(keys1)):
    res[keys1[idx]] = vals2[idx]

# printing result 
print("Mapped dictionary : " + str(res)) 
```

**Output**

> 原词典 1 为:{'Gfg': 20，' is': 36，' best': 100}
> 原词典 2 为:{'Gfg2': 26，' is2': 19，' best2': 70}
> 映射词典:{'Gfg': 26，' is': 19，' best': 70}

**方法 2:使用 zip() + values()**

这是执行这项任务的另一种方式。在本文中，我们使用 zip()执行映射任务，使用 values()提取值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Assign similar index values in Dictionary
# Using zip() + values()

# initializing dictionaries
test_dict1 = {"Gfg" : 20, "is" : 36, "best" : 100}
test_dict2 = {"Gfg2" : 26, "is2" : 19, "best2" : 70}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# using zip() to perform required dict. mapping 
res = dict(zip(test_dict1, test_dict2.values()))

# printing result 
print("Mapped dictionary : " + str(res)) 
```

**Output**

> 原词典 1 为:{'Gfg': 20，' is': 36，' best': 100}
> 原词典 2 为:{'Gfg2': 26，' is2': 19，' best2': 70}
> 映射词典:{'Gfg': 26，' is': 19，' best': 70}