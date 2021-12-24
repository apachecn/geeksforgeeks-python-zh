# Python–检查是否存在对应于 K 键的特定值

> 原文:[https://www . geesforgeks . org/python-check-if-special-value-present-对应于-k-key/](https://www.geeksforgeeks.org/python-check-if-particular-value-is-present-corresponding-to-k-key/)

给定一个字典列表，检查特定的键值对是否存在。

> **输入**:[{“Gfg”:“4”、“is”:“好”、“最佳”:“1”}、{“Gfg”:“9”、“is”:“CS”、“最佳”:“10”}]、K =“Gfg”、val =“find”
> **输出** : False
> **解释**:无值的“Gfg”为“find”。
> 
> **输入**:[{“Gfg”:“4”，“是”:“好”，“最好”:“1”}，{“Gfg”:“9”，“是”:“CS”，“最好”:“10”}]，K =“Gfg”，val = 4
> **输出**:真
> **解释** : 4 呈现为“Gfg”值。

**方法一:使用列表理解**

这是执行这项任务的方法之一。在这种情况下，我们使用列表理解提取字典，然后使用“In”运算符检查其中是否有任何值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Check if particular value is present corresponding to K key
# Using list comprehension

# initializing lists
test_list = [{"Gfg" : "4", "is" : "good", "best" : "1"},
             {"Gfg" : "find", "is" : "better", "best" : "8"},
             {"Gfg" : "9", "is" : "CS", "best" : "10"}]

# printing original list
print("The original list : " + str(test_list))

# initializing K key
K = "Gfg"

# initializing target value
val = "find"

# extracting values using list comprehension
# using in operator to check for values
res = val in [sub[K] for sub in test_list]

# printing result
print("Is key-val pair present?  : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': '4', 'is': 'good', 'best': '1'}, {'Gfg': 'find', 'is': 'better', 'best': '8'}, {'Gfg': '9', 'is': 'CS', 'best': '10'}]
Is key-val pair present?  : True
```

**方法 2:在运算符**中使用 map() +

这是执行这项任务的另一种方式。在这个任务中，获取对应于特定键的值是使用 map()执行的，将函数扩展到每个字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Check if particular value is present corresponding to K key
# Using map() + in operator

# initializing lists
test_list = [{"Gfg" : "4", "is" : "good", "best" : "1"},
             {"Gfg" : "find", "is" : "better", "best" : "8"},
             {"Gfg" : "9", "is" : "CS", "best" : "10"}]

# printing original list
print("The original list : " + str(test_list))

# initializing K key
K = "Gfg"

# initializing target value
val = "find"

# extracting values using map
# using in operator to check for values
res = val in list(map(lambda sub : sub[K], test_list))

# printing result
print("Is key-val pair present?  : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': '4', 'is': 'good', 'best': '1'}, {'Gfg': 'find', 'is': 'better', 'best': '8'}, {'Gfg': '9', 'is': 'CS', 'best': '10'}]
Is key-val pair present?  : True
```