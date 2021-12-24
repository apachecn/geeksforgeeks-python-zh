# Python–在字典开头追加项目

> 原文:[https://www . geeksforgeeks . org/python-append-items-at-期初词典/](https://www.geeksforgeeks.org/python-append-items-at-beginning-of-dictionary/)

给定一部词典，在它的开头附加另一部词典。

> **输入**:test _ dict = {“Gfg”:5、“is”:3、“best”:10 }、upd ICT = {“pre 1”:4 }
> **输出**:{“pre 1”:4、“Gfg”:5、“is”:3、“best”:10 }
> **解释**:词典前更新新词典。
> 
> **输入**:test _ dict = {“Gfg”:5 }，upd ICT = {“pre 1”:4 }
> **输出**:{“pre 1”:4、‘Gfg】:5 }
> **解释**:词典前更新新词典，“pre 1”:4。

**方法#1:使用 update()**

这是执行这项任务的方法之一。在这种情况下，我们使用 update 函数在新字典之后更新旧字典，以便在开始时追加新字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Append items at beginning of dictionary 
# Using update()

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 3, "best" : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing update dictionary
updict = {"pre1" : 4, "pre2" : 8}

# update() on new dictionary to get desired order
updict.update(test_dict)

# printing result 
print("The required dictionary : " + str(updict)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 5, 'is': 3, 'best': 10}
The required dictionary : {'pre1': 4, 'pre2': 8, 'Gfg': 5, 'is': 3, 'best': 10}

```

**方法 2:使用**运算符**

这是执行这项任务的另一种方式。在这种情况下，我们使用**操作符将项目打包和解包到定制字典中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Append items at beginning of dictionary 
# Using ** operator

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 3, "best" : 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing update dictionary
updict = {"pre1" : 4, "pre2" : 8}

# ** operator for packing and unpacking items in order
res = {**updict, **test_dict}

# printing result 
print("The required dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 5, 'is': 3, 'best': 10}
The required dictionary : {'pre1': 4, 'pre2': 8, 'Gfg': 5, 'is': 3, 'best': 10}

```