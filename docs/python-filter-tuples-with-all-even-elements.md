# Python–过滤所有偶数元素的元组

> 原文:[https://www . geeksforgeeks . org/python-filter-元组-带全偶元素/](https://www.geeksforgeeks.org/python-filter-tuples-with-all-even-elements/)

给定元组列表，只过滤所有偶数元素的元组。

> **输入** : test_list = [(6，4，2，8)，(5，6，7，6)，(8，1，2)，(7)，]
> **输出** : [(6，4，2，8)]
> **解释**:只有 1 个元组，包含所有偶数元素。
> 
> **输入** : test_list = [(6，4，2，9)，(5，6，7，6)，(8，1，2)，(7)，]
> **输出** : []
> **解释**:没有包含所有偶数元素的元组。

**方法#1:使用循环**

在这种情况下，我们迭代每个元组，并使用%运算符检查所有偶数元素，如果偶数元素是奇数，元组被标记，而不是添加到结果列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter Tuples with All Even Elements
# Using loop

# initializing list
test_list = [(6, 4, 2, 8), (5, 6, 7, 6), (8, 0, 2), (7, )]

# printing original list
print("The original list is : " + str(test_list))

res_list = []
for sub in test_list:
    res = True 

    # check if all are even
    for ele in sub:
        if ele % 2 != 0:
            res = False
            break
    if res:
        res_list.append(sub)

# printing results
print("Filtered Tuples : " + str(res_list))
```

**Output**

```
The original list is : [(6, 4, 2, 8), (5, 6, 7, 6), (8, 0, 2), (7, )]
Filtered Tuples : [(6, 4, 2, 8), (8, 0, 2)]

```

**方法 2:使用 all() +列表理解**

在这种情况下，检查所有元素是否均匀的任务是使用 all()完成的，列表理解用于过滤后检查的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter Tuples with All Even Elements
# Using all() + list comprehension

# initializing list
test_list = [(6, 4, 2, 8), (5, 6, 7, 6), (8, 0, 2), (7, )]

# printing original list
print("The original list is : " + str(test_list))

# testing for tuple to be even using all()
res = [sub for sub in test_list if all(ele % 2 == 0 for ele in sub)]

# printing results
print("Filtered Tuples : " + str(res))
```

**Output**

```
The original list is : [(6, 4, 2, 8), (5, 6, 7, 6), (8, 0, 2), (7, )]
Filtered Tuples : [(6, 4, 2, 8), (8, 0, 2)]

```