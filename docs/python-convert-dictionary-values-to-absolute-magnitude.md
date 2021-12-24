# Python–将字典值转换为绝对值

> 原文:[https://www . geesforgeks . org/python-convert-dictionary-values-to-absolute-magic/](https://www.geeksforgeeks.org/python-convert-dictionary-values-to-absolute-magnitude/)

给定一个字典，将其值转换为绝对值。

> **输入**:test _ dict = {“Gfg”:-5、“is”:-7、“Best”:-2 }
> **输出**:{“Gfg”:5、“is”:7、“Best”:2 }
> **解释**:所有负元素变为正，幅度相同
> 
> **输入**:test _ dict = {“Gfg”:-8、“是”:7、“最佳”:-2}
> **输出**:{“Gfg”:8、“是”:7、“最佳”:2}
> **解释**:所有负元素都变成了同量级的正

**方法#1:使用 loop + abs()**

这是执行这项任务的方法之一。在本文中，我们使用循环迭代字典的每个值，并使用 abs()执行绝对幅度转换。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert Dictionary values to Absolute Magnitude
# Using loop + abs()

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : -7, "Best" : 2, "for" : -9, "geeks" : -8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using abs() to perform conversion
# from negative to positive values
for ele in test_dict:
    test_dict[ele] = abs(test_dict[ele])

# printing result
print("Dictionary after absolute conversion : " + str(test_dict))
```

**Output**

```py
The original dictionary is : {'Gfg': 5, 'is': -7, 'Best': 2, 'for': -9, 'geeks': -8}
Dictionary after absolute conversion : {'Gfg': 5, 'is': 7, 'Best': 2, 'for': 9, 'geeks': 8}
```

**方法 2:使用词典理解+ abs()**

这个任务类似于上面的方法。区别在于字典理解被用来代替循环来执行通过键迭代的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert Dictionary values to Absolute Magnitude
# Using dictionary comprehension + abs()

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : -7, "Best" : 2, "for" : -9, "geeks" : -8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# dictionary comprehension using to compile result
# items() used to extract dictionary keys and values.
res = {key : abs(val) for key, val in test_dict.items()}

# printing result
print("Dictionary after absolute conversion : " + str(res))
```

**Output**

```py
The original dictionary is : {'Gfg': 5, 'is': -7, 'Best': 2, 'for': -9, 'geeks': -8}
Dictionary after absolute conversion : {'Gfg': 5, 'is': 7, 'Best': 2, 'for': 9, 'geeks': 8}
```