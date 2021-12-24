# Python–连接字符串列表中的范围值

> 原文:[https://www . geesforgeks . org/python-concatenate-ranged-values-in-string-list/](https://www.geeksforgeeks.org/python-concatenate-ranged-values-in-string-list/)

给定字符串列表，执行字符串列表中范围值的连接。

> **输入**:test _ list =[“ABgfgcs”、“cdforef”、“asalloi”]，I，j = 3，5
> **输出** : FGorll
> **解释**:从所有三个字符串中切分出所有字符串，FG，or 和 ll 并连接。
> 
> **输入**:test _ list =[“aGFGcs”、“cforef”、“a loi”]，I，j = 1，4
> **输出** : GFGforall
> **解释**:类似切片操作不同范围。

**方法一:使用循环+字符串切片**

这是执行这项任务的粗暴方式。在本文中，我们对所有字符串进行迭代，并对每个字符串的范围值进行串联。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Concatenate Ranged Values in String list
# Using loop

# initializing list
test_list = ["abGFGcs", "cdforef", "asalloi"]

# printing original list
print("The original list : " + str(test_list))

# initializing range
i, j = 2, 5

res = ''
for ele in test_list:

    # Concatenating required range
    res += ele[i : j]

# printing result 
print("The Concatenated String : " + str(res))
```

**Output**

```
The original list : ['abGFGcs', 'cdforef', 'asalloi']
The Concatenated String : GFGforall

```

**方法二:使用列表理解+字符串切片**

这是执行这项任务的另一种方式。在这种情况下，我们使用上述列表理解和字符串切片方法在一行中提取特定范围的字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Concatenate Ranged Values in String list
# Using list comprehension + string slicing

# initializing list
test_list = ["abGFGcs", "cdforef", "asalloi"]

# printing original list
print("The original list : " + str(test_list))

# initializing range
i, j = 2, 5

# join() used to join slices together
res = ''.join([sub[i : j] for sub in test_list])

# printing result 
print("The Concatenated String : " + str(res))
```

**Output**

```
The original list : ['abGFGcs', 'cdforef', 'asalloi']
The Concatenated String : GFGforall

```