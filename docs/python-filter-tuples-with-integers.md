# Python–用整数过滤元组

> 原文:[https://www . geesforgeks . org/python-filter-元组-with-integers/](https://www.geeksforgeeks.org/python-filter-tuples-with-integers/)

给定元组列表，过滤只有 int 数据类型的元组。

> **输入** : [(4，5，“GFg”)、(3)、、(“Gfg”、)]
> **输出** : [(3)、]
> **解释** : 1 元组(3)，，全部为整数值。
> 
> **输入** : [(4，5，“Gfg”)、(3，“Best”)、(“GFg”、)]
> **输出** : []
> **解释**:没有包含所有整数的元组。

**方法#1:使用 loop + isinstance()**

在这种情况下，我们迭代每个元组，并使用 isinstance()检查除 int 之外的数据类型，如果找到的元组被标记为 off 并被省略。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter Tuples with Integers
# Using loop + isinstance()

# initializing list
test_list = [(4, 5, "GFg"), (5, 6), (3, ), ("Gfg", )]

# printing original list
print("The original list is : " + str(test_list))

res_list = []
for sub in test_list:
    res = True 
    for ele in sub:

        # checking for non-int.
        if not isinstance(ele, int):
            res = False 
            break
    if res :
        res_list.append(sub)

# printing results
print("Filtered tuples : " + str(res_list))
```

**Output**

```
The original list is : [(4, 5, 'GFg'), (5, 6), (3, ), ('Gfg', )]
Filtered tuples : [(5, 6), (3, )]

```

**方法 2:使用 all() +列表理解+ isinstance()**

在这种情况下，all()用于使用 isinstance()检查所有元素是否都是整数，如果检查，则将元组添加到结果中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter Tuples with Integers
# Using all() + list comprehension + isinstance()

# initializing list
test_list = [(4, 5, "GFg"), (5, 6), (3, ), ("Gfg", )]

# printing original list
print("The original list is : " + str(test_list))

# list comprehension to encapsulate in 1 liner 
res = [sub for sub in test_list if all(isinstance(ele, int) for ele in sub)]

# printing results
print("Filtered tuples : " + str(res))
```

**Output**

```
The original list is : [(4, 5, 'GFg'), (5, 6), (3, ), ('Gfg', )]
Filtered tuples : [(5, 6), (3, )]

```