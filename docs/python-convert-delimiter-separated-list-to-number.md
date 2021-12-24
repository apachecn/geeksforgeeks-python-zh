# Python–将分隔符分隔的列表转换为数字

> 原文:[https://www . geesforgeks . org/python-convert-delimiter-separated-list-to-number/](https://www.geeksforgeeks.org/python-convert-delimiter-separated-list-to-number/)

给定一个带分隔符的字符串，去掉分隔符后连接成整数。

> **输入**:test _ str =“1 @ 6 @ 7 @ 8”，delim =“@”
> **输出** : 1678
> **解释**:去掉 delim 后的连接元素“@”
> **输入**:test _ str =“1！6!7!8 "，delim = '！'
> **输出** : 1678
> **说明**:去掉 delim 后的连接元素“！”

**方法#1:使用循环+拆分()+ int()**

这是执行这项任务的方法之一。在这种情况下，我们在分隔符上拆分字符串，然后运行一个循环来连接，最后结果被转换为 int()。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Delimiter separated list to Number
# Using loop + split() + join()

# initializing string
test_str = "1@6@7@8@5@8@9"

# printing original string
print("The original string is : " + str(test_str))

# initializing Delimiter
delim = "@"

# spliting to get list of string numbers
temp = test_str.split(delim)
res = ''
for ele in temp:
    res = res + ele

# converting result into integer
res = int(res)

# printing result
print("Constructed integer : " + str(res))
```

**Output**

```
The original string is : 1@6@7@8@5@8@9
Constructed integer : 1678589
```

**方法 2:使用 join() + split() + int()**

这是执行这项任务的另一种方式。在本例中，我们使用 join()和 int()执行最终连接，以获得最终结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Delimiter separated list to Number
# Using join() + split() + int()

# initializing string
test_str = "1@6@7@8@5@8@9"

# printing original string
print("The original string is : " + str(test_str))

# initializing Delimiter
delim = "@"

# join used over splitted result
# final result casted using int()
res = int("".join(test_str.split(delim)))

# printing result
print("Constructed integer : " + str(res))
```

**Output**

```
The original string is : 1@6@7@8@5@8@9
Constructed integer : 1678589
```