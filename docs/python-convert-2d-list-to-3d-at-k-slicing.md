# Python–在 K 切片时将 2D 列表转换为 3D

> 原文:[https://www . geesforgeks . org/python-convert-2d-list-to-3d-at-k-slicing/](https://www.geeksforgeeks.org/python-convert-2d-list-to-3d-at-k-slicing/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要在每个 Kth 列表中将 2D 列表转换为 3D。这种类型的问题很特殊，但可以应用于各种数据领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [[6，5]，[2，3]，[3，1]，[4，6]，[3，2]，[1，6]]，K = 3
> **输出**:[[6，5]，[2，3]，[3，1]]，[[4，6]，[3，2]，[1，6]]
> 
> **输入** : test_list = [[6，5]，[2，3]，[3，1]]，K = 1
> **输出** : [[[6，5]]，[[2，3]]，[[3，1]]

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们遍历每个元素，并在每个 Kth 子列表中维护一个计数器，创建一个新列表并相应地追加。

```
# Python3 code to demonstrate working of 
# Convert 2D list to 3D at K slicing
# Using loop

# initializing list
test_list = [[6, 5], [2, 3], [3, 1], [4, 6], [3, 2], [1, 6]] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# Convert 2D list to 3D at K slicing
# Using loop
res = []
subl = []
cnt = 0
for sub in test_list:
    subl.append(sub)
    cnt = cnt + 1
    if cnt >= K:
        res.append(subl)
        subl = []
        cnt = 0

# printing result 
print("Records after conversion : " + str(res))
```

**Output :**

```
The original list is : [[6, 5], [2, 3], [3, 1], [4, 6], [3, 2], [1, 6]]
Records after conversion : [[[6, 5], [2, 3]], [[3, 1], [4, 6]], [[3, 2], [1, 6]]]

```

**方法二:使用`zip()` +列表理解**
以上功能的组合也可以用来解决这个问题。在这种情况下，我们通过首先根据大小对值进行分块来执行任务，然后使用列表理解和 zip()进行维度转换。

```
# Python3 code to demonstrate working of 
# Convert 2D list to 3D at K slicing
# Using zip() + list comprehension

# initializing list
test_list = [[6, 5], [2, 3], [3, 1], [4, 6], [3, 2], [1, 6]] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# Convert 2D list to 3D at K slicing
# Using zip() + list comprehension
test_list = iter(test_list)
temp = [test_list] * K
res = [list(ele) for ele in zip(*temp)]

# printing result 
print("Records after conversion : " + str(res))
```

**Output :**

```
The original list is : [[6, 5], [2, 3], [3, 1], [4, 6], [3, 2], [1, 6]]
Records after conversion : [[[6, 5], [2, 3]], [[3, 1], [4, 6]], [[3, 2], [1, 6]]]

```