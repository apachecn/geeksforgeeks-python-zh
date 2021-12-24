# 如何在 Python 中创建字典列表

> 原文:[https://www . geesforgeks . org/如何创建 python 词典列表/](https://www.geeksforgeeks.org/how-to-create-list-of-dictionary-in-python/)

在本文中，我们将讨论用 Python 创建字典列表的方法。

字典列表意味着，字典作为一个元素出现在列表中。

**语法:**

> [{'key':element1，' key':element2，…，' key':element n}]

**示例:** Python 代码为学生数据创建一个字典列表

## 蟒蛇 3

```
# create a list of dictionary with student
# id as key and name as value
data = [{7058: 'sravan', 7059: 'jyothika',
         7072: 'harsha', 7075: 'deepika'}]

# display data
data
```

**输出:**

> [{7058:'女士'，7059: 'jyothika '，7072: 'harsha '，7075: 'deepika'}]

我们可以通过使用索引来访问

**语法:**

> 数据[索引][密钥]

其中 index 是字典索引，key 是字典键值

**示例:**通过索引访问密钥的 Python 代码

## 蟒蛇 3

```
# create a list of dictionary with student 
# id as key and name as value
data = [{7058: 'sravan', 7059: 'jyothika', 
         7072: 'harsha', 7075: 'deepika'}]

# display data of key 7058
print(data[0][7058])

# display data of key 7059
print(data[0][7059])

# display data of key 7072
print(data[0][7072])

# display data of key 7075
print(data[0][7075])
```

**输出:**

```
sravan
jyothika
harsha
deepika
```

## 多本词典列表

这类似于上面的方法，除了同时向列表传递多个字典。

**示例:** Python 程序创建多个字典的列表

## 蟒蛇 3

```
# create a list of dictionaries with 
# student id as key and name as value
data = [{7058: 'sravan', 7059: 'jyothika', 
         7072: 'harsha', 7075: 'deepika'},

        {7051: 'fathima', 7089: 'mounika', 
         7012: 'thanmai', 7115: 'vasavi'},

        {9001: 'ojaswi', 1289: 'daksha', 
         7045: 'parvathi', 9815: 'bhavani'}]

print(data)
```

**输出:**

> [{ 7058:’s van '，7059: 'jyothika '，7072:` har sha '，7075:` deepika ' }，{ 7051:` fathima '，7089:` mounika '，7012:` thanmai '，7115:` vasavi ' }，{ 9001:` ojas wi '，1289:` dak sha '，705:` Parvati '，9815:` bhavani ' }]

它可以再次使用索引访问所有元素。

**示例:**基于索引和键访问元素的 Python 代码

## 蟒蛇 3

```
# create a list of dictionaries with 
# student id as key and name as value
data = [{7058: 'sravan', 7059: 'jyothika',
         7072: 'harsha', 7075: 'deepika'},

        {7051: 'fathima', 7089: 'mounika', 
         7012: 'thanmai', 7115: 'vasavi'},

        {9001: 'ojaswi', 1289: 'daksha', 
         7045: 'parvathi', 9815: 'bhavani'}]

# access third dictionary wih key 9001
print(data[2][9001])

# access second dictionary wih key 7012
print(data[1][7012])

# access second dictionary wih key 7115
print(data[1][7115])
```

**输出:**

```
ojaswi
thanmai
vasavi
```