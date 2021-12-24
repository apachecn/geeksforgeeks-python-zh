# Python–过滤唯一值元组

> 原文:[https://www . geesforgeks . org/python-filter-unique-value-元组/](https://www.geeksforgeeks.org/python-filter-unique-valued-tuples/)

给定元组列表，过滤不包含重复的元组。

> **输入** : test_list = [(3，5，6，7)，(3，2，4，3)，(9，4，9)，(2，3，2)]
> **输出** : [(3，5，6，7)]
> **:其余所有元组均有重复值。**
> 
> ****输入** : test_list = [(3，5，6，7，7)，(3，2，4，3)，(9，4，9)，(2，3，2)]
> **输出** : []
> **解释**:所有元组都有重复值。**

****方法#1:使用循环+ set()****

**在这种情况下，所有的元组都被迭代，并使用 set()进行双重测试，如果 set 的长度与元组相同，则不包含重复。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of 
# Filter unique valued tuples
# Using loop + set()

# initializing list
test_list = [(3, 5, 6, 7), (3, 2, 4, 3), (9, 4), (2, 3, 2)]

# printing original list
print("The original list is : " + str(test_list))

res = []

for sub in test_list:

    # checking lengths to be equal
    if len(set(sub)) == len(sub):
        res.append(sub)

# printing results
print("Filtered tuples : " + str(res))
```

****Output**

```
The original list is : [(3, 5, 6, 7), (3, 2, 4, 3), (9, 4), (2, 3, 2)]
Filtered tuples : [(3, 5, 6, 7), (9, 4)]

```** 

****方法 2:使用列表理解****

**这执行与上面类似的任务，不同的是这是一个线性和紧凑。**

## **蟒蛇 3**

```
# Python3 code to demonstrate working of 
# Filter unique valued tuples
# Using list comprehension

# initializing list
test_list = [(3, 5, 6, 7), (3, 2, 4, 3), (9, 4), (2, 3, 2)]

# printing original list
print("The original list is : " + str(test_list))

# list comprehension used to filter
res = [sub for sub in test_list if len(set(sub)) == len(sub)]

# printing results
print("Filtered tuples : " + str(res))
```

****Output**

```
The original list is : [(3, 5, 6, 7), (3, 2, 4, 3), (9, 4), (2, 3, 2)]
Filtered tuples : [(3, 5, 6, 7), (9, 4)]

```**