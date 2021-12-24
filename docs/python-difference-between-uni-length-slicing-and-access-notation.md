# Python–单一长度切片和访问符号的区别

> 原文:[https://www . geesforgeks . org/python-uni-length-slicing-and-access-notification/](https://www.geeksforgeeks.org/python-difference-between-uni-length-slicing-and-access-notation/)

有各种各样的方法来提取元素，Uni 长度切片和访问符号就是其中之一。让我们检查一下它们之间的区别。

**差异#1:不同容器的不同行为**

访问符号返回列表和字符串中的元素，但在使用单长度切片和字符串情况下的元素进行切片时返回 1 长度的字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Difference between Uni length slicing and Access Notation
# In different containers

# initializing lists
test_list = [5, 7, 2, 6, 8, 1]

# initializing string 
test_str = "572681"

# printing original list
print("The original list : " + str(test_list))

# printing string
print("The original string : " + str(test_str))
print("\r")

# access Notation results 
acc_list = test_list[3]
acc_str = test_str[3]

# unilength slicing results 
slc_list = test_list[3 : 4]
slc_str = test_str[3 : 4]

# printing results 
print("The access notation result for list : " + str(acc_list))
print("The access notation result for string : " + str(acc_str))
print("\r")
print("The slicing result for list : " + str(slc_list))
print("The slicing result for string : " + str(slc_str))
```

**Output**

```py
The original list : [5, 7, 2, 6, 8, 1]
The original string : 572681

The access notation result for list : 6
The access notation result for string : 6

The slicing result for list : [6]
The slicing result for string : 6

```

**差异#2:切片操作时无索引越界异常**

在切片操作的情况下没有越界异常，但是在访问标记的情况下有。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Difference between Uni length slicing and Access Notation
# No Index out of bounds Exception in case of Slice operation

# initializing lists
test_list = [5, 7, 2, 6, 8, 1]

# printing string
print("The original list : " + str(test_list))

# access Notation results 
try :
    acc_list = test_list[17]
except Exception as e:
    acc_list = str(e)

# unilength slicing results 
slc_list = test_list[17 : 18]

# printing results 
print("The access notation result for list : " + str(acc_list))
print("The slicing result for list : " + str(slc_list))
```

**Output**

```py
The original list : [5, 7, 2, 6, 8, 1]
The access notation result for list : list index out of range
The slicing result for list : []

```