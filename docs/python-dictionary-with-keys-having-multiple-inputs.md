# 带多输入键的 Python 字典

> 原文:[https://www . geesforgeks . org/python-带键字典-具有多个输入/](https://www.geeksforgeeks.org/python-dictionary-with-keys-having-multiple-inputs/)

先决条件:[Python-字典](https://www.geeksforgeeks.org/python-dictionary/)。

**如何创建使用输入形成键的字典？**
让我们考虑一个例子，我们有一个方程，用于三个输入变量，x，y 和 z。我们想要存储不同输入三元组的方程值。

**例 1:**

## 蟒蛇 3

```
# Python code to demonstrate a dictionary
# with multiple inputs in a key.
import random as rn

# creating an empty dictionary
dict = {}

# Insert first triplet in dictionary
x, y, z = 10, 20, 30
dict[x, y, z] = x + y - z;

# Insert second triplet in dictionary
x, y, z = 5, 2, 4
dict[x, y, z] = x + y - z;

# print the dictionary
print(dict)
```

**示例 2:** 让我们获取密钥。
让我们考虑一个字典，其中经度和纬度是**键**，它们所属的地方是**值**。

## 蟒蛇 3

```
# dictionary containing longitude and latitude of places
places = {("19.07'53.2", "72.54'51.0"):"Mumbai", \
          ("28.33'34.1", "77.06'16.6"):"Delhi"}

print(places)
print('\n')

# Traversing dictionary with multi-keys and creating
# different lists from it
lat = []
long = []
plc = []
for i in places:
    lat.append(i[0])
    long.append(i[1])
    plc.append(places[i[0], i[1]])

print(lat)
print(long)
print(plc)
```

现在键(纬度、经度)和值(地点)都存储在一个列表中，我们可以很容易地访问它。