# Python–提取频率相等的元素作为值

> 原文:[https://www . geeksforgeeks . org/python-提取等频值元素/](https://www.geeksforgeeks.org/python-extract-elements-with-equal-frequency-as-value/)

给定一个列表，提取与其值具有相同频率的所有元素。

**示例:**

> **输入** : test_list = [4，3，2，2，3，4，1，3，2，4，4]
> **输出**:【1，3，4】
> **解释**:所有元素出现的次数与其值相等。
> 
> **输入** : test_list = [4，3，2，2，3，4，1，3，2，4]
> **输出**:【1，3】
> **解释**:所有元素出现的次数与其值相等。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**计数()**](https://www.geeksforgeeks.org/python-string-count/)

在这种情况下，获取频率的任务是使用 count()完成的，列表理解用于对每个元素进行迭代、比较和提取。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract elements with equal frequency as value
# Using list comprehension + count()

# initializing list
test_list = [4, 3, 2, 2, 3, 4, 1, 3, 2, 4, 4]

# printing original list
print("The original list is : " + str(test_list))

# removing duplicates using set()
# count() for computing frequency
res = list(set([ele for ele in test_list if test_list.count(ele) == ele]))

# printing result 
print("Filtered elements : " + str(res))
```

**Output**

```
The original list is : [4, 3, 2, 2, 3, 4, 1, 3, 2, 4, 4]
Filtered elements : [1, 3, 4]

```

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+计数()**

在本例中，我们使用 filter()和 lambda 执行过滤元素的任务，count()再次用于获取所有元素的计数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract elements with equal frequency as value
# Using filter() + lambda + count()

# initializing list
test_list = [4, 3, 2, 2, 3, 4, 1, 3, 2, 4, 4]

# printing original list
print("The original list is : " + str(test_list))

# removing duplicates using set()
# count() for computing frequency
# filter used to perform filtering 
res = list(set(list(filter(lambda ele : test_list.count(ele) == ele, test_list))))

# printing result 
print("Filtered elements : " + str(res))
```

**Output**

```
The original list is : [4, 3, 2, 2, 3, 4, 1, 3, 2, 4, 4]
Filtered elements : [1, 3, 4]

```