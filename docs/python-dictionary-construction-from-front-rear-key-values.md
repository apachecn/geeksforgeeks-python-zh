# Python–从前后键值开始构建字典

> 原文:[https://www . geesforgeks . org/python-dictionary-construction-from-from-from-back-key-values/](https://www.geeksforgeeks.org/python-dictionary-construction-from-front-rear-key-values/)

给定一个列表，使用关键字作为前半部分值和从后半部分开始的值来构建字典。

> **输入** : test_list = [4，10，5，3]
> **输出** : {4: 3，10: 5}
> **说明**:前(4)与后(3)配对，以此类推。
> 
> **输入** : test_list = [5，3]
> **输出** : {5: 3}
> **说明**:前(5)与后(3)配对。

> **输入** : test_dict = {“苹果”:2、“芒果”:2、“葡萄”:2}、{“苹果”:2、“芒果”:2、“葡萄”:2}
> **输出** : 12
> **解释** : (2*2) + (2*2) + (2*2) = 12。
> 
> **输入** : test_dict = {“苹果”:3、“芒果”:2、“葡萄”:3}、{“苹果”:2、“芒果”:2、“葡萄”:2}
> **输出** : 16
> **解释**:积的求和得出 16 如上。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们从头开始运行一个循环，从 beg-end 中提取值，并相应地构造键值映射。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary construction from front-rear key values
# Using loop

# initializing list
test_list = [4, 6, 3, 10, 5, 3]

# printing original list
print("The original list : " + str(test_list))

# initializing size and empty Dictionary
n = len(test_list)
res = dict()

# running loop till mid
for idx in range(n // 2):

    # mapping as required
    res.__setitem__(test_list[idx], test_list[n - idx - 1]) 

# printing result 
print("The mapped dictionary : " + str(res))
```

**Output**

```py
The original list : [4, 6, 3, 10, 5, 3]
The mapped dictionary : {4: 3, 6: 5, 3: 10}

```

**方法 2:使用 zip() + dict()**

这是执行这项任务的另一种方式。在本例中，我们使用 zip()执行压缩键和值元素的任务，dict()用于将结果转换为字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary construction from front-rear key values
# Using zip() + dict()

# initializing list
test_list = [4, 6, 3, 10, 5, 3]

# printing original list
print("The original list : " + str(test_list))

# using zip to cut first and second half 
n = len(test_list)
res = dict(zip(test_list[:n // 2], test_list[n // 2:][::-1]))

# printing result 
print("The mapped dictionary : " + str(res))
```

**Output**

```py
The original list : [4, 6, 3, 10, 5, 3]
The mapped dictionary : {4: 3, 6: 5, 3: 10}

```