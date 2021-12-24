# Python–将元组值列表转换为元组列表

> 原文:[https://www . geesforgeks . org/python-convert-tuple-value-list-to-list-of-tuples/](https://www.geeksforgeeks.org/python-convert-tuple-value-list-to-list-of-tuples/)

给定一个值为元组列表的字典，转换为键映射的元组列表。

> **输入** : test_dict = {'Gfg' : [(5，6，7)，(6)，]，' is' : [(5，5，2，2，6)]，' best' :[(7，]}
> **输出** : [('Gfg '，5，6，7)，(' Gfg '，6)，(' is '，5，5，2，2，6)，(' best '，7)]
> **解释**:按值分组的按键。
> 
> **输入** : test_dict = {'Gfg' : [(5，，(6)，]，' is' : [(5，]，' best' :[(7，]}
> **输出** : [('Gfg '，5)、(' Gfg '，6)、(' is '，5)、(' best '，7)]
> **解释**:按值分组的按键。

**方法#1:使用循环+ *运算符+项()**

这是执行这项任务的方法之一。在本文中，我们使用循环迭代所有键，并通过使用*运算符解包元组中的所有值来将键与所有值映射。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Tuple value list to List of tuples
# Using loop + * operator + items()

# initializing dictionary
test_dict = {'Gfg' : [(5, 6, 7), (1, 3), (6, )],
             'is' : [(5, 5, 2, 2, 6)], 
             'best' :[(7, ), (9, 16)]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using items() to extract all the items of 
# dictionary
res = []
for key, val in test_dict.items():
    for ele in val:
        res.append((key, *ele))

# printing result 
print("The converted tuple list : " + str(res)) 
```

**Output**

> 原字典为:{'Gfg': [(5，6，7)，(1，3)，(6)，]，' is': [(5，5，2，2，6)]，' best': [(7)，(9，16)]}
> 转换后的元组列表:[('Gfg '，5，6，7)，(' Gfg '，1，3)，(' Gfg '，6)，(' is '，5，5，2，2，6)，(' best '，7)、(' best '，9，16)]

**方法 2:使用列表理解+ *运算符+项目()**

这是解决这个问题的另一种方法。以与上述方法类似的方式求解。唯一的区别是使用列表理解提供了一个线性解决方案。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Tuple value list to List of tuples
# Using list comprehension + * operator + items()

# initializing dictionary
test_dict = {'Gfg' : [(5, 6, 7), (1, 3), (6, )],
             'is' : [(5, 5, 2, 2, 6)], 
             'best' :[(7, ), (9, 16)]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# list comprehension encapsulates whole logic 
# into one line
res = [(key, *ele) for key, sub in test_dict.items() for ele in sub]

# printing result 
print("The converted tuple list : " + str(res)) 
```

**Output**

> 原字典为:{'Gfg': [(5，6，7)，(1，3)，(6)，]，' is': [(5，5，2，2，6)]，' best': [(7)，(9，16)]}
> 转换后的元组列表:[('Gfg '，5，6，7)，(' Gfg '，1，3)，(' Gfg '，6)，(' is '，5，5，2，2，6)，(' best '，7)、(' best '，9，16)]