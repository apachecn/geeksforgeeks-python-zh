# Python–提取最大键的值字典

> 原文:[https://www . geesforgeks . org/python-extract-maximum-key-value-dictionary/](https://www.geeksforgeeks.org/python-extract-maximum-keys-value-dictionaries/)

给定一个字典，提取字典列表中所有包含最大值的任意键的字典。

> **输入**:[{“Gfg”:3，“是”:7，“最佳”:8}，{“Gfg”:9，“是”:2，“最佳”:9}，{“Gfg”:5，“是”:4，“最佳”:10}，{“Gfg”:3，“是”:6，“最佳”:14}]
> **输出**:[{“Gfg”:3，“是”:7，“最佳”:8}，{“Gfg”:9，“是”:2，“最佳”:9}，{“Gfg”:3，“是”
> 
> **输入**:[{“Gfg”:3，“是”:7，“最佳”:8}，{“Gfg”:9，“是”:2，“最佳”:9}，{“Gfg”:5，“是”:4，“最佳”:10}，{“Gfg”:3，“是”:6，“最佳”:16}]
> **输出**:[{“Gfg”:3，“是”:7，“最佳”:8}，{“Gfg”:9，“是”:2，“最佳”:9}，{“Gfg”:3，“是”

**方法:使用 max() + filter() + lambda**

上述功能的组合可以用来解决这个问题。在这种情况下，首先为特定关键字提取最大值，然后提取匹配最大值关键字的所有字典。这是为所有钥匙执行的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Maximum Keys' value dictionaries
# Using max() + filter() + lambda

# initializing list
test_list = [{"Gfg" : 3, "is" : 7, "Best" : 8}, 
             {"Gfg" : 9, "is" : 2, "Best" : 9}, 
             {"Gfg" : 5, "is" : 4, "Best" : 10},
             {"Gfg" : 3, "is" : 6, "Best" : 8}]

# printing original list
print("The original list : " + str(test_list))

res = []

# getting all keys 
all_keys = list(test_list[0].keys())
for sub in all_keys:

    # extracting maximum of each keys
    temp = max(test_list, key = lambda ele: ele[sub]) 
    res_key = list(filter(lambda ele: ele[sub] == temp[sub], test_list))
    res.append(res_key)

# printing result 
print("The extracted maximum key values dictionaries : " + str(res))
```

**Output**

```
The original list : [{'Gfg': 3, 'is': 7, 'Best': 8}, {'Gfg': 9, 'is': 2, 'Best': 9}, {'Gfg': 5, 'is': 4, 'Best': 10}, {'Gfg': 3, 'is': 6, 'Best': 8}]
The extracted maximum key values dictionaries : [[{'Gfg': 9, 'is': 2, 'Best': 9}], [{'Gfg': 3, 'is': 7, 'Best': 8}], [{'Gfg': 5, 'is': 4, 'Best': 10}]]

```