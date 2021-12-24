# Python–K 中间元素

> 原文:[https://www.geeksforgeeks.org/python-k-middle-elements/](https://www.geeksforgeeks.org/python-k-middle-elements/)

给定一个列表，提取列表中间出现的 K 个元素。

> **输入** : test_list = [2，3，5，7，8，5，3，5，9]，K = 3
> **输出**:【7，8，5】
> **解释**:提取中间 3 个元素。
> 
> **输入** : test_list = [2，3，5，7，8，5，3，5，9]，K = 7
> **输出**:【3，5，7，8，5，3，5】
> **解释**:提取中间 7 个元素。

**方法#1:使用循环**

在这种情况下，我们首先制定范围，提取一半前中间，一半后中间元素，然后使用循环提取所需的元素。在奇数长度列表中均匀工作。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# K middle elements
# Using loop

# initializing list
test_list = [2, 3, 5, 7, 8, 5, 3, 5, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# computing strt, and end index 
strt_idx = (len(test_list) // 2) - (K // 2)
end_idx = (len(test_list) // 2) + (K // 2)

# using loop to get indices 
res = []
for idx in range(len(test_list)):

    # checking for elements in range
    if idx >= strt_idx and idx <= end_idx:
        res.append(test_list[idx])

# printing result 
print("Extracted elements list : " + str(res))
```

**Output**

```
The original list is : [2, 3, 5, 7, 8, 5, 3, 5, 9]
Extracted elements list : [5, 7, 8, 5, 3]

```

**方法二:使用** [**列表切片**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，在范围计算步骤之后，使用列表切片进行范围提取。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# K middle elements
# Using list slicing 

# initializing list
test_list = [2, 3, 5, 7, 8, 5, 3, 5, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# computing strt, and end index 
strt_idx = (len(test_list) // 2) - (K // 2)
end_idx = (len(test_list) // 2) + (K // 2)

# slicing extracting middle elements
res = test_list[strt_idx: end_idx + 1]

# printing result 
print("Extracted elements list : " + str(res))
```

**Output**

```
The original list is : [2, 3, 5, 7, 8, 5, 3, 5, 9]
Extracted elements list : [5, 7, 8, 5, 3]

```