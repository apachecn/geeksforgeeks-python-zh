# Python–差分排序字符串数字和字母

> 原文:[https://www . geesforgeks . org/python-differential-sort-string-numbers-and-alphabets/](https://www.geeksforgeeks.org/python-differential-sort-string-numbers-and-alphabets/)

给定一个列表字符串，重新排序列表，排序的字母后面跟着排序的字符串。

> **输入**:test _ list =【“1”、“G”、“10”、“L”、“9”、“K”、“4”】
> **输出**:【‘G’、‘K’、‘L’、‘1’、‘4’、‘9’、‘10’】
> **说明:**字母排序，按排序位数排序成功。
> 
> **输入**:test _ list =[“1”、“G”、“10”、“L”、“9”]
> **输出**:[‘G’、‘L’、‘1’、‘9’、‘10’]
> **解释**:字母排序，按排序后的数字排序成功。

**方法#1:使用 isnumeric() +循环**

在这种情况下，我们使用 isnumeric()将数字和字母字符分开，然后对每个列表执行排序，然后对两个列表执行连接以获得结果。仅适用于 1 位数的字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Differential Sort String Numbers and Alphabets
# Using isnumeric() + loop

# initializing list
test_list = ["1", "G", "7", "L", "9", "M", "4"]

# printing original list
print("The original list is : " + str(test_list))

numerics = []
alphabets = []
for sub in test_list:

    # checking and inserting in respective container
    if sub.isnumeric():
        numerics.append(sub)
    else:
        alphabets.append(sub)

# attaching lists post sort
res = sorted(alphabets) + sorted(numerics)

# printing result
print("The Custom sorted result : " + str(res))
```

**Output**

```py
The original list is : ['1', 'G', '7', 'L', '9', 'M', '4']
The Custom sorted result : ['G', 'L', 'M', '1', '4', '7', '9']
```

**方法 2:使用 sorted() + isnumeric()**

这是解决这个问题的一种线性方法，它使用 isnumeric 检查数字，并使用 sorted()执行 sort()。将元素转换为整数并进行测试，可以处理 1 位数以上的数字。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Differential Sort String Numbers and Alphabets
# Using sorted() + isnumeric()

# initializing list
test_list = ["100", "G", "74", "L", "98", "M", "4"]

# printing original list
print("The original list is : " + str(test_list))

# using int() to type convert to integer
# using sorted() to perform sort operation
res = sorted(test_list, key = lambda ele: (ele.isnumeric(), int(ele) if ele.isnumeric() else ele))

# printing result
print("The Custom sorted result : " + str(res))
```

**Output**

```py
The original list is : ['100', 'G', '74', 'L', '98', 'M', '4']
The Custom sorted result : ['G', 'L', 'M', '4', '74', '98', '100']
```