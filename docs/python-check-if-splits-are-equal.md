# Python–检查拆分是否相等

> 原文:[https://www . geesforgeks . org/python-check-if-splits-equal/](https://www.geeksforgeeks.org/python-check-if-splits-are-equal/)

给定由 delim 分隔的字符串，检查所有拆分是否相似。

> **输入**:' 45 # 45 # 45′，delim = '#'
> **输出**:真
> **解释**:均等于 45。
> 
> **输入** : '4@5@5 '，delim = '@'
> **输出**:假
> **说明**:第一段等于 4，休息 5。

**方法#1:使用 set() + len() + split()**

在这种情况下，我们执行拆分以获取列表格式的元素，然后转换为集合，删除重复的元素，并检查 len == 1，确认所有元素都相同。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Check if Splits are equal
# Using set() + len() + split()

# initializing string
test_str = '45# 45# 45# 45# 45'

# printing original string
print("The original string is : " + str(test_str))

# initializing splt_chr 
splt_chr = "#"

# checking for length of set obtained, res stores boolean result
res = len(list(set(test_str.split(splt_chr)))) == 1

# printing result 
print("Are all splits equal ? : " + str(res)) 
```

**Output**

```
The original string is : 45#45#45#45#45
Are all splits equal ? : True

```

**方法 2:使用 split() + all()**

在本例中，我们使用 all()执行检查所有元素是否相等的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Check if Splits are equal
# Using split() + all()

# initializing string
test_str = '45# 45# 45# 45# 45'

# printing original string
print("The original string is : " + str(test_str))

# initializing splt_chr 
splt_chr = "#"

# splitting using split()
new_list = test_str.split(splt_chr)

# checking all equal to 1st element
res = all(ele == new_list[0] for ele in new_list)

# printing result 
print("Are all splits equal ? : " + str(res)) 
```

**Output**

```
The original string is : 45#45#45#45#45
Are all splits equal ? : True

```