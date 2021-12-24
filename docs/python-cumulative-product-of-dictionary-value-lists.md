# Python–字典值列表的累积乘积

> 原文:[https://www . geeksforgeeks . org/python-累积词典产品价值列表/](https://www.geeksforgeeks.org/python-cumulative-product-of-dictionary-value-lists/)

有时，在使用 Python 字典时，我们可以将它的值作为列表。在这种情况下，我们可能会有一个问题，我们只需要这些列表中元素的乘积作为一个整体。这可能是数据科学中的一个问题，在数据科学中，我们需要获得观察中的全部记录。让我们讨论一下执行这个任务的某些方式
**方法#1:使用循环+列表理解**
这个任务可以使用显式乘积函数来执行，该函数可以用来获取乘积，内部列表理解可以提供一个机制来将这个逻辑迭代到字典的所有键。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Cumulative product of dictionary value lists
# using loop + list comprehension

def prod(val) :    
    res = 1        
    for ele in val:        
        res *= ele        
    return res

# initialize dictionary
test_dict = {'gfg' : [5, 6, 7], 'is' : [10, 11], 'best' : [19, 31, 22]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Cumulative product of dictionary value lists
# using loop + list comprehension
res = sum(prod(sub) for sub in test_dict.values())

# printing result
print("Product of dictionary list values are : " + str(res))
```

**Output : **

```
The original dictionary is : {'best': [19, 31, 22], 'gfg': [5, 6, 7], 'is': [10, 11]}
Product of dictionary list values are : 13278
```

**方法#2:使用 loop + map()**
这个任务也可以使用 map 函数代替列表理解来执行，扩展查找产品的逻辑，其余所有功能保持与上述方法相同。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Cumulative product of dictionary value lists
# using loop + map()

def prod(val) :    
    res = 1        
    for ele in val:        
        res *= ele        
    return res

# initialize dictionary
test_dict = {'gfg' : [5, 6, 7], 'is' : [10, 11], 'best' : [19, 31, 22]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Cumulative product of dictionary value lists
# using loop + map()
res = sum(map(prod, test_dict.values()))

# printing result
print("Product of dictionary list values are : " + str(res))
```

**Output : **

```
The original dictionary is : {'best': [19, 31, 22], 'gfg': [5, 6, 7], 'is': [10, 11]}
Product of dictionary list values are : 13278
```