# Python–列表中的平均位数

> 原文:[https://www . geesforgeks . org/python-平均位数-列表中的计数/](https://www.geeksforgeeks.org/python-average-digits-count-in-a-list/)

给定一个元素列表，提取列表中的平均位数。

> **输入** : test_list = [34，2345，23，456，2，23，456787]
> **输出** : 2.857142857142857
> **解释**:所有位数的平均值。[2+4+2+3+1+2+6 = 20, 20/7 = 2.857142857142857]
> 
> **输入** : test_list = [34，1，456]
> **输出** : 2.0
> **解释**:所有位数的平均值。[1 + 2 + 3 = 6，6 / 3 = 2]

**方法#1:使用**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+loop+**[**str()**](https://www.geeksforgeeks.org/python-str-function/)

在这种情况下，我们迭代每个元素，转换成字符串，并找到它的长度，使用计数器执行求和，然后将结果与列表中的总元素相除以获得结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Average digits count
# Using len() + loop + str()

# initializing list
test_list = [34, 2345, 23, 456, 2, 23, 456787]

# printing original list
print("The original list is : " + str(test_list))

sumd = 0
for ele in test_list:

    # summing digits length 
    sumd += len(str(ele))

# getting result after dividing total digits by elements    
res = sumd / len(test_list)

# printing result 
print("Average digits length : " + str(res))
```

**Output**

```py
The original list is : [34, 2345, 23, 456, 2, 23, 456787]
Average digits length : 2.857142857142857

```

**方法 2:使用 len()+**[**sum()**](https://www.geeksforgeeks.org/sum-function-python/)**+str()**

在这种情况下，获取和的任务是使用 sum()完成的，扩展了一种解决问题的紧凑方法。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Average digits count
# Using len() + sum() + str()

# initializing list
test_list = [34, 2345, 23, 456, 2, 23, 456787]

# printing original list
print("The original list is : " + str(test_list))

# getting summation and dividing by total length
res = sum([len(str(ele)) for ele in test_list]) / len(test_list)

# printing result 
print("Average digits length " + str(res))
```

**Output**

```py
The original list is : [34, 2345, 23, 456, 2, 23, 456787]
Average digits length 2.857142857142857

```