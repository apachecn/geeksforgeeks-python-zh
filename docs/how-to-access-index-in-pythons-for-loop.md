# 如何在 Python 的 for 循环中访问索引

> 原文:[https://www . geesforgeks . org/如何访问循环蟒蛇索引/](https://www.geeksforgeeks.org/how-to-access-index-in-pythons-for-loop/)

在本文中，我们将讨论在 Python 中为循环访问索引。

### 我们可以通过以下方式访问索引:

1.  使用索引元素
2.  使用枚举()
3.  使用列表理解
4.  使用 zip()

Index 元素用于表示元素在列表中的位置。这里我们通过元素列表访问索引

## **使用索引元素**

这里，我们使用迭代器变量来遍历列表。

## 蟒蛇 3

```py
# create a list of subjects
data = ["java", "python", "HTML", "PHP"]

print("Indices in the list:")

# display indices in the list
for i in range(len(data)):
    print(i)

print("Index values in the list:")
# display each index value in the list
for i in range(len(data)):
    print(data[i])
```

**输出:**

```py
Indices in the list:
0
1
2
3
Index values in the list:
java
python
HTML
PHP
```

## **使用枚举()方法**

此方法用于 for 循环，该循环用于获取索引以及该范围内的相应元素。

## 计算机编程语言

```py
# create a list of subjects
data = ["java", "python", "HTML", "PHP"]

print("Indices and values in list:")

# get the indices and values using enumerate method
for i in enumerate(data):
    print(i)
```

**输出:**

```py
Indices and values in list:
(0, 'java')
(1, 'python')
(2, 'HTML')
(3, 'PHP')
```

## **使用列表理解法**

这将列出索引，然后给出索引和索引值。

## 蟒蛇 3

```py
# create a list of subjects
data = ["java", "python", "HTML", "PHP"]

print("Indices in list:")

# get the indices  using list comprehension method
print([i for i in range(len(data))])

print("values in list:")

# get the values from indices  using list
# comprehension method
print([data[i] for i in range(len(data))])
```

**输出:**

```py
Indices in list:
[0, 1, 2, 3]
values in list:
['java', 'python', 'HTML', 'PHP']
```

## 使用 zip()方法

Zip 方法用于一次压缩索引和值，我们必须传递两个列表，一个是索引元素列表，另一个是元素列表

## 蟒蛇 3

```py
# create a index list that stores list
indexlist = [0, 1, 2, 3]

# create a list of subjects
data = ["java", "python", "HTML", "PHP"]

print("index and values in list:")

# get the values from indices  using zip method
for index, value in zip(indexlist, data):
    print(index, value)
```

**输出:**

```py
index and values in list:
0 java
1 python
2 HTML
3 PHP
```