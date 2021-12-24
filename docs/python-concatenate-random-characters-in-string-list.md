# Python–连接字符串列表中的随机字符

> 原文:[https://www . geesforgeks . org/python-concatenate-随机字符串列表/](https://www.geeksforgeeks.org/python-concatenate-random-characters-in-string-list/)

给定一个字符串列表，执行随机字符的连接。

> **输入**:test _ list =[“Gfg”、“is”、“Best”、“for”、“Geeks”]
> **输出**:“GiBfe”
> **解释**:随机选择的元素，如从 Gfg 中选 G 等。
> **输入**:test _ list =[“Gfg”、“is”、“Best”]
> **输出**:“FST”
> **解释**:随机选择的元素，如:来自 Best 的 t 等。

**方法#1:使用循环+随机选择()**

在本文中，我们使用 choice()提取随机字符，并使用循环执行迭代任务。字符连接使用+运算符完成。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Concatenate Random characters in String List
# Using loop + choice()
import random

# initializing list
test_list = ["Gfg", "is", "Best", "for", "Geeks"]

# printing original list
print("The original list is : " + str(test_list))

res = ''
for ele in test_list:

    # Concatenating random elements
    res += random.choice(ele)

# printing results
print("Concatenated String : " + str(res))
```

**Output**

```py
The original list is : ['Gfg', 'is', 'Best', 'for', 'Geeks']
Concatenated String : Gsere
```

**方法 2:使用列表理解+选择()+连接()**

在本例中，我们使用 choice()执行获取随机数的任务，并使用 join()完成连接。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Concatenate Random characters in String List
# Using list comprehension + choice() + join()
import random

# initializing list
test_list = ["Gfg", "is", "Best", "for", "Geeks"]

# printing original list
print("The original list is : " + str(test_list))

# characters joining using join()
res = ''.join([random.choice(ele) for ele in test_list])

# printing results
print("Concatenated String : " + str(res))
```

**Output**

```py
The original list is : ['Gfg', 'is', 'Best', 'for', 'Geeks']
Concatenated String : Gitrk
```