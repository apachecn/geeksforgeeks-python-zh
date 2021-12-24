# Python–提取子串匹配的索引

> 原文:[https://www . geesforgeks . org/python-extract-indexs-of-substring-matches/](https://www.geeksforgeeks.org/python-extract-indices-of-substring-matches/)

给定一个字符串列表和一个子字符串，提取该子字符串所在的字符串索引列表。

> **输入**:test _ list =[“Gfg 好”、“给极客”、“我爱 Gfg”、“Gfg 有用”]，K =“Gfg”
> **输出**:【0，2，3】
> **解释**:“Gfg”作为子串出现在第 0、2、3 个元素中。
> 
> **输入**:test _ list =[“Gfg 好”、“给极客”、“我爱 Gfg”、“Gfg 有用”]，K =“好”
> **输出**:【0】
> **解释**:“好”出现在第 0 个子串。

**方法 2:使用循环+枚举()**

这是完成这项任务的粗暴方式。在这种情况下，我们使用枚举()迭代所有元素及其索引，并使用条件语句来获得所需的结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Indices of substring matches
# Using loop + enumerate()

# initializing list
test_list = ["Gfg is good", "for Geeks", "I love Gfg", "Its useful"]

# initializing K 
K = "Gfg"

# printing original list
print("The original list : " + str(test_list))

# using loop to iterate through list 
res = []
for idx, ele in enumerate(test_list):
  if K in ele:
    res.append(idx)

# printing result 
print("The indices list : " + str(res))
```

**Output**

```py
The original list : ['Gfg is good', 'for Geeks', 'I love Gfg', 'Its useful']
The indices list : [0, 2]

```

**方法 2:使用列表理解+枚举()**

这是解决这一任务的另一种方法。在这种情况下，我们使用列表理解来执行与上述方法类似的任务，并使用 enumerate()来获得紧凑解。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Indices of substring matches
# Using list comprehension + enumerate()

# initializing list
test_list = ["Gfg is good", "for Geeks", "I love Gfg", "Its useful"]

# initializing K 
K = "Gfg"

# printing original list
print("The original list : " + str(test_list))

# using list comprehension and enumerate to offer compact solution
res = [idx for idx, val in enumerate(test_list) if K in val]

# printing result 
print("The indices list : " + str(res))
```

**Output**

```py
The original list : ['Gfg is good', 'for Geeks', 'I love Gfg', 'Its useful']
The indices list : [0, 2]

```