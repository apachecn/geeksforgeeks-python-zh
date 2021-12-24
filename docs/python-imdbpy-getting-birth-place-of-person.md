# Python IMDbPY–获取人的出生地

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-出生地-人/](https://www.geeksforgeeks.org/python-imdbpy-getting-birth-place-of-person/)

在本文中，我们将看到如何从 person 对象中获取人的出生地，imdb person 对象的行为类似于字典，因此，从 person 对象中获取出生地类似于从字典中获取所需信息。

> 为此，我们必须执行以下操作–
> 1。使用 get_person 方法
> 2 借助 id 获取人物对象。使用结果['出生信息']['出生地点']作为关键字获得出生地点
> 3。打印结果

下面是实现:

## 蟒蛇 3

```py
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

# getting birth place
place = actor['birth info']['birth place']

# printing the place
print(place)
```

**输出:**

```py
Shahid Kapoor
New Delhi, India
```

另一个例子:

## 蟒蛇 3

```py
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

# getting birth place
place = actor['birth info']['birth place']

# printing the place
print(place)
```

**输出:**

```py
Nawazuddin Siddiqui
Budhana, Muzaffarnagar, Uttar Pradesh, India
```