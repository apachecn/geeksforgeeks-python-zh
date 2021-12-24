# Python IMDbPY–获取人名的替代名称

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-alternate-人名/](https://www.geeksforgeeks.org/python-imdbpy-getting-alternate-names-of-person/)

在本文中，我们将了解如何从 person 对象中获取人名的替代名称，替代名称基本上是给他们起的昵称或艺名，即他们被称为的名称，imdb person 对象的行为类似于字典，因此从 person 对象中获取图像类似于从字典中获取所需信息。

> 为此，我们必须执行以下操作–
> 1。使用 get_person 方法
> 2 借助 id 获取人物对象。使用结果['akas']作为关键字
> 3 从中获取替代名称。打印结果

**注意:**输出将是图像的链接即字符串数据类型不是实际图像
下面是实现

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
code = "1596350"

# getting person object
actor = ia.get_person(code)

# printing object it prints its name
print(actor)

# getting alternate names
alternate = actor['akas']

# printing
print(alternate)
```

**输出:**

```
Nawazuddin Siddiqui
['Nawazuddin', 'Novaz', 'Nowaz', 'Nawazuddin Siddique', 'Nawaz Uddin']
```

另一个例子

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
code = "1372788"

# getting person object
actor = ia.get_person(code)

# printing object it prints its name
print(actor)

# getting alternate names
alternate = actor['akas']

# printing
print(alternate)
```

**输出:**

```
Shahid Kapoor
['Shahid Kapur', 'Shahid']
```