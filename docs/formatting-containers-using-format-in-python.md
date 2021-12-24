# 使用 Python 中的 format()格式化容器

> 原文:[https://www . geesforgeks . org/formatting-containers-使用 python 中的格式/](https://www.geeksforgeeks.org/formatting-containers-using-format-in-python/)

让我们看看如何使用 Python 中的 **format()** 方法格式化通过 __getitem__ 或 getattr()访问的容器。

## 访问支持 __getitem__ 的容器

#### 对于词典

## 蟒蛇 3

```py
# creating a dictionary
founder = {'Apple': 'Steve Jobs', 'Microsoft': 'Bill Gates'}

# formatting
print('{f[Microsoft]} {f[Apple]}'.format(f = founder))
```

**输出:**

```py
Bill Gates Steve Jobs

```

f[微软]被比尔·盖茨取代，f[苹果]被史蒂夫·乔布斯取代。

#### 对于名单

## 蟒蛇 3

```py
# creating a list
list_items = [1, 3, 5, 7, 9, 11]

# formatting
print('{l[3]} {l[5]}'.format(l = list_items))
```

**输出:**

```py
7 11

```

## 访问支持 getattr()的对象的属性

#### 为了上课

## 蟒蛇 3

```py
# creating a class
class Program(object):
    language = 'Python'

# formatting
print('{p.language}'.format(p = Program()))
```

**输出:**

```py
Python

```

由于语言是程序的属性，所以用 Python 代替了 p 语言

**访问嵌套结构**

## 蟒蛇 3

```py
# creating a clas
class Program(object):
    language = 'Python'

    # creating a dictionary
    versions = [{'version': '1'}, {'version': '2'}, {'version': '3'}]

# formatting
print('{p.language}: {p.versions[2][version]}'.format(p = Program()))
```

**输出:**

```py
Python: 3

```