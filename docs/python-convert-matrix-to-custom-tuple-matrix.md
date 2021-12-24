# Python–将矩阵转换为自定义元组矩阵

> 原文:[https://www . geesforgeks . org/python-convert-matrix-to-custom-tuple-matrix/](https://www.geeksforgeeks.org/python-convert-matrix-to-custom-tuple-matrix/)

有时，在使用 Python Matrix 时，我们可能会遇到一个问题，即我们需要执行 Python Matrix 到元组矩阵的转换，元组矩阵是从外部列表按行定制的值。这种问题可以在数据领域中应用，因为矩阵是所使用的整数。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [[4，5]，[7，3]]，add_list = ['Gfg '，' best']
> **输出** : [('Gfg '，4)、(' Gfg '，5)、(' best '，7)、(' best '，3)]
> 
> **输入** : test_list = [[4，5]]，add_list = ['Gfg']
> **输出** : [('Gfg '，4)，(' Gfg，5)]

**方法#1:使用 loop + `zip()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 zip()执行将自定义值绑定到行的每个元素的任务。这是执行这项任务的蛮力方式。

```
# Python3 code to demonstrate working of 
# Convert Matrix to Custom Tuple Matrix
# Using zip() + loop

# initializing lists
test_list = [[4, 5, 6], [6, 7, 3], [1, 3, 4]]

# printing original list
print("The original list is : " + str(test_list))

# initializing List elements 
add_list = ['Gfg', 'is', 'best']

# Convert Matrix to Custom Tuple Matrix
# Using zip() + loop
res = []
for idx, ele in zip(add_list, test_list):
    for e in ele:
        res.append((idx, e))

# printing result 
print("Matrix after conversion : " + str(res))
```

**Output :**

> 原列表为:[[4，5，6]，[6，7，3]，[1，3，4]]
> 转换后的矩阵:[('Gfg '，4)、(' Gfg '，5)、(' Gfg '，6)、(' is '，6)、(' is '，7)、(' is '，3)、(' best '，1)、(' best '，3)、(' best '，4)]

**方法 2:使用列表理解+ `zip()`**
这是可以执行该任务的又一种方式。在这种情况下，我们执行与上述方法类似的任务，只是作为一种速记。

```
# Python3 code to demonstrate working of 
# Convert Matrix to Custom Tuple Matrix
# Using list comprehension + zip()

# initializing lists
test_list = [[4, 5, 6], [6, 7, 3], [1, 3, 4]]

# printing original list
print("The original list is : " + str(test_list))

# initializing List elements 
add_list = ['Gfg', 'is', 'best']

# Convert Matrix to Custom Tuple Matrix
# Using list comprehension + zip()
res = [(ele1, ele2) for ele1, sub in zip(add_list, test_list) for ele2 in sub]

# printing result 
print("Matrix after conversion : " + str(res)) 
```

**Output :**

> 原列表为:[[4，5，6]，[6，7，3]，[1，3，4]]
> 转换后的矩阵:[('Gfg '，4)、(' Gfg '，5)、(' Gfg '，6)、(' is '，6)、(' is '，7)、(' is '，3)、(' best '，1)、(' best '，3)、(' best '，4)]