# Python–具有相同索引的元素

> 原文:[https://www . geesforgeks . org/python-elements-with-same-index/](https://www.geeksforgeeks.org/python-elements-with-same-index/)

给定一个列表，获取在其索引值的所有元素。

> **输入** : test_list = [3，1，8，5，4，10，6，9]
> **输出** : [1，4，6]
> **解释**:这些元素与其编号处于同一位置。
> 
> **输入** : test_list = [3，10，8，5，14，10，16，9]
> **输出** : []
> **解释**:其索引处无数字。

**方法#1:使用循环**

在这种情况下，我们检查每个元素，如果它等于它的索引，它就被添加到结果列表中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Elements with same index
# Using loop

# initializing list
test_list = [3, 1, 2, 5, 4, 10, 6, 9]

# printing original list
print("The original list is : " + str(test_list))

# enumerate to get index and element
res = []
for idx, ele in enumerate(test_list):
    if idx == ele:
        res.append(ele)

# printing result 
print("Filtered elements : " + str(res))
```

**Output**

```py
The original list is : [3, 1, 2, 5, 4, 10, 6, 9]
Filtered elements : [1, 2, 4, 6]

```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)

在这种情况下，我们执行与上述方法类似的功能，改变是我们使用列表理解来使解决方案紧凑。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Elements with same index
# Using list comprehension + enumerate()

# initializing list
test_list = [3, 1, 2, 5, 4, 10, 6, 9]

# printing original list
print("The original list is : " + str(test_list))

# enumerate to get index and element
res = [ele for idx, ele in enumerate(test_list) if idx == ele]

# printing result 
print("Filtered elements : " + str(res))
```

**Output**

```py
The original list is : [3, 1, 2, 5, 4, 10, 6, 9]
Filtered elements : [1, 2, 4, 6]

```