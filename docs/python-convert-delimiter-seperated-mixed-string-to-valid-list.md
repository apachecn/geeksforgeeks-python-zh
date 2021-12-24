# Python–将分隔符分隔的混合字符串转换为有效列表

> 原文:[https://www . geesforgeks . org/python-convert-delimiter-separated-mixed-string-to-valid-list/](https://www.geeksforgeeks.org/python-convert-delimiter-seperated-mixed-string-to-valid-list/)

给定一个包含元素和分隔符的字符串，在分隔符上拆分元素以提取元素(包括容器)。

> **输入** : test_str = "6*2*9*[3，5，6]*(7，8)*8*4*10 "，delim = " *
> **输出**:【6，2，9，[3，5，6]，(7，8)，8，4，10]
> **解释**:容器和元素用*分隔开。
> 
> **输入** : test_str = "[3，5，6]*(7，8)*8*4*10 "，delim = " *
> **输出** : [[3，5，6]，(7，8)，8，4，10]
> **解释**:使用*分隔的容器和元素。

**方法#1:使用循环+ eval() + split()**

这是完成这项任务的一种方法。在这种情况下，分离是使用 split()完成的，eval()执行的重要任务是将数据类型评估为容器或更简单的元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert delimiter separated Mixed String to valid List
# Using loop + split() + eval()

# initializing string
test_str = "6# 2# 9#[3, 5, 6]#(7, 8)# 8# 4# 10"

# printing original string
print("The original string is : " + str(test_str))

# initializing delim
delim = "#"

# splitting using split()
temp = test_str.split(delim)
res = []

# using loop + eval() to convert to
# required result
for ele in temp:
  res.append(eval(ele))

# printing result
print("List after conversion : " + str(res))
```

**Output**

```
The original string is : 6#2#9#[3, 5, 6]#(7, 8)#8#4#10
List after conversion : [6, 2, 9, [3, 5, 6], (7, 8), 8, 4, 10]
```

**方法 2:使用 eval() + split() +列表理解**

这是执行这项任务的另一种方式。在这种情况下，我们执行与上述方法类似的任务。唯一的区别是整个逻辑被列表理解封装成一个线性。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert delimiter separated Mixed String to valid List
# Using eval() + split() + list comprehension

# initializing string
test_str = "6# 2# 9#[3, 5, 6]#(7, 8)# 8# 4# 10"

# printing original string
print("The original string is : " + str(test_str))

# initializing delim
delim = "#"

# encapsulating entire result in list comprehension
res = [eval(ele) for ele in test_str.split(delim)]

# printing result
print("List after conversion : " + str(res))
```

**Output**

```
The original string is : 6#2#9#[3, 5, 6]#(7, 8)#8#4#10
List after conversion : [6, 2, 9, [3, 5, 6], (7, 8), 8, 4, 10]
```