# Python–创建元组列表

> 原文:[https://www . geesforgeks . org/python-创建元组列表/](https://www.geeksforgeeks.org/python-create-a-list-of-tuples/)

在本文中，我们将讨论在 Python 中创建元组列表的多种方法。

## **方法 1:使用 list()和 tuple()方法**

我们可以直接使用 list 和元组来创建元组列表。

**语法:**

> [(tuple1)、(tuple2)、(tuple3)、..，(元组 n)]

**示例:**使用列表和元组创建元组列表的 Python 代码

## 蟒蛇 3

```py
# create tuples with college id and
# name and store in a list
data = [(1, 'sravan'), (2, 'ojaswi'), (3, 'bobby'),
        (4, 'rohith'), (5, 'gnanesh')]

# display data
data
```

**输出:**

> [(1，' sravan '，(2，' ojaswi ')，(3，' bobby ')，(4，' rohith '，(5，' gnanesh')]

## **方法二:使用** [**zip()**](https://www.geeksforgeeks.org/zip-in-python/) **功能**

使用 zip()函数，我们可以从 n 个列表中创建一个元组列表。

**语法:**

> 列表(zip(列表 1，列表 2，.，列表)

这里，列表是数据(单独的列表，是列表中像元组这样的元素

**示例:** Python 程序创建两个具有学院 id 和名称的列表，并使用 zip()函数创建元组列表

## 蟒蛇 3

```py
# create two lists  with college id and name
roll_no = [1, 2, 3, 4, 5]
name = ['sravan', 'ojaswi', 'bobby', 'rohith', 'gnanesh']

# zip the two lists using zip() function
data = list(zip(roll_no, name))

# display data
data
```

**输出:**

> [(1，' sravan '，(2，' ojaswi ')，(3，' bobby ')，(4，' rohith '，(5，' gnanesh')]

## **方法三:使用 zip()和**[**ITER()**](https://www.geeksforgeeks.org/python-iter-method/)T6】方法

这里我们将使用 iter()函数和 zip()函数形成一个元组列表。

**语法:**

> [x 代表邮政编码中的 x(*[ITER(列表)]]

其中 x 是要在列表中迭代的迭代器，zip 用于压缩列表，iter()用于迭代整个列表

**示例:**通过形成元组列表来创建元组列表的 Python 代码

## 蟒蛇 3

```py
# create a list with name
name = ['sravan', 'ojaswi', 'bobby', 'rohith', 'gnanesh']

# zip the two lists using iter() function
data = [x for x in zip(*[iter(name)])]

# display data
data
```

**输出:**

> [(' s van '，(' ojaswi '，)，(' bobby '，(' rohith '，)，(' gnanesh ')

## **方法四:使用** [**地图()**](https://www.geeksforgeeks.org/python-map-function/) **功能**

在这里，我们在列表中传递数据，然后使用 map()函数，我们可以创建一个元组列表

**语法:**

> 列表(映射(元组，列表数据))

这里，list_data 是创建元组列表的输入列表，list 是预定义函数，元组是预定义函数

**示例:**使用 map()函数从列表中创建元组列表的 Python 代码

## 蟒蛇 3

```py
# create a list with name
name = [['sravan'], ['ojaswi'], ['bobby'], 
        ['rohith'], ['gnanesh']]

# create list of tuple using above 
# list using map function
data = list(map(tuple, name))

# display data
data
```

**输出:**

> [(' s van '，(' ojaswi '，)，(' bobby '，(' rohith '，)，(' gnanesh ')

## **方法五:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **和元组()方法**

这里我们使用理解和元组来创建元组列表。

**语法:**

> [列表数据中 x 的元组(x )]

其中 tuple(x)是将迭代对象转换为 tuple 的迭代器，list_data 是输入数据

**示例:**使用列表理解和 tuple()方法创建元组列表的 Python 代码

## 蟒蛇 3

```py
# create a list with name
name = [['sravan'], ['ojaswi'], ['bobby'],
        ['rohith'], ['gnanesh']]

# create list of tuple using above list
# using  list comprehension and tuple() 
# method
data = [tuple(x) for x in name]

# display data
data
```

**输出:**

> [(' s van '，(' ojaswi '，)，(' bobby '，(' rohith '，)，(' gnanesh ')