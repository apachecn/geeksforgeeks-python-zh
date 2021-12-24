# Python 字典 popitem()方法

> 原文:[https://www . geesforgeks . org/python-dictionary-pop item-method/](https://www.geeksforgeeks.org/python-dictionary-popitem-method/)

**Python 字典 popitem()方法**从字典中移除最后插入的键值对，并将其作为元组返回。

> **语法**关闭.泼皮()
> 
> **参数:**无
> 
> **从字典中返回:**包含任意键值对的元组。那对已从词典中删除。

生成随机数在日常生活中有很多应用。在列表中，支持相同的各种功能。一整个库都专用于 **Python 处理随机数**。但有时，我们需要用字典执行类似的任务。

**注意:**如果字典为空，popitem()方法返回 keyError。

## Python 字典 popitem()方法示例

### **示例#1:** 演示 popitem()的使用

这里我们将使用 **python 字典在最后**元素中打开项目。

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# working of popitem()

# initializing dictionary
test_dict = {"Nikhil": 7, "Akshat": 1, "Akash": 2}

# Printing initial dict
print("The dictionary before deletion : " + str(test_dict))

# using popitem() to return + remove arbitrary
# pair
res = test_dict.popitem()

# Printing the pair returned
print('The arbitrary pair returned is : ' + str(res))

# Printing dict after deletion
print("The dictionary after removal : " + str(test_dict))
```

**输出:**

```py
The dictionary before deletion : {'Nikhil': 7, 'Akshat': 1, 'Akash': 2}
The arbitrary pair returned is : ('Akash', 2)
The dictionary after removal : {'Nikhil': 7, 'Akshat': 1}
```

**实际应用:**这个特殊的函数可以在不使用任何随机函数的情况下，用于制定玩游戏的随机名称或决定随机排名。

### **示例#2:** 演示 popitem()的应用

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# application of popitem()

# initializing dictionary
test_dict = {"Nikhil": 7, "Akshat": 1, "Akash": 2}

# Printing initial dict
print("The dictionary before deletion : " + str(test_dict))

n = len(test_dict)

# using popitem to assign ranks
for i in range(0, n):
    print("Rank " + str(i + 1) + " " + str(test_dict.popitem()))

# Printing end dict
print("The dictionary after deletion : " + str(test_dict))
```

**输出:**

```py
The dictionary before deletion : {'Nikhil': 7, 'Akshat': 1, 'Akash': 2}
Rank 1 ('Akash', 2)
Rank 2 ('Akshat', 1)
Rank 3 ('Nikhil', 7)
The dictionary after deletion : {}
```

### 示例 3: Python 字典 popitem 随机

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get random dictionary pair in dictionary
# Using popitem()

# Initialize dictionary
test_dict = {'Gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Get random dictionary pair in dictionary
# Using popitem()
res = test_dict.popitem()

# printing result
print("The random pair is : " + str(res))
```

**输出:**

```py
The original dictionary is : {'Gfg': 1, 'best': 3, 'is': 2}
The random pair is : ('is', 2)
```