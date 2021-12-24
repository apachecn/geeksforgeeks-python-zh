# Python–更改列表中元组元素的符号

> 原文:[https://www . geeksforgeeks . org/python-列表中元组元素的变化符号/](https://www.geeksforgeeks.org/python-change-signs-of-elements-of-tuples-in-a-list/)

给定一个双元组列表，任务是编写一个 python 程序，将第二个元素转换为每个元组的负幅度，将第一个元素转换为每个元组的正幅度。

> **输入:** test_list = [(3，-1)、(-4，-3)、(1，3)、(-2，5)、(-4，2)、(-9，-3)]
> 
> **输出:** [(3，-1)，(4，-3)，(1，-3)，(2，-5)，(4，-2)，(9，-3)]
> 
> **说明:**根据需要，第一个元素全部为正，第二个索引元素为负。
> 
> **输入** : test_list = [(3，-1)，(-4，-3)，(1，3)，(-2，5)]
> 
> **输出:** [(3，-1)，(4，-3)，(1，-3)，(2，-5)]
> 
> **说明:**根据需要，第一个元素全部为正，第二个索引元素为负。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*abs()*](https://www.geeksforgeeks.org/abs-in-python/)

在本文中，我们使用循环进行迭代，并使用 abs()将两者初始转换为正幅度。第二个元素带符号“-”，并根据需要转换为负元素。

**示例:**

## 蟒蛇 3

```py
# initializing lists
test_list = [(3, -1), (-4, -3), (1, 3), (-2, 5), (-4, 2), (-9, -3)]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:

    # 2nd element converted to negative magnitude
    res.append((abs(sub[0]), -abs(sub[1])))

# printing result
print("Updated Tuple list : " + str(res))
```

**输出:**

> 原列表为:[(3，-1)，(-4，-3)，(1，3)，(-2，5)，(-4，2)，(-9，-3)]
> 
> 更新的元组列表:[(3，-1)，(4，-3)，(1，-3)，(2，-5)，(4，-2)，(9，-3)]

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

与上述方法类似，唯一的区别是列表理解被用作执行此任务的一个衬垫。

**示例:**

## 蟒蛇 3

```py
# initializing lists
test_list = [(3, -1), (-4, -3), (1, 3), (-2, 5), (-4, 2), (-9, -3)]

# printing original list
print("The original list is : " + str(test_list))

# list comprehension used as one liner
res = [(abs(sub[0]), -abs(sub[1])) for sub in test_list]

# printing result
print("Updated Tuple list : " + str(res))
```

**输出:**

> 原列表为:[(3，-1)，(-4，-3)，(1，3)，(-2，5)，(-4，2)，(-9，-3)]
> 
> 更新的元组列表:[(3，-1)，(4，-3)，(1，-3)，(2，-5)，(4，-2)，(9，-3)]