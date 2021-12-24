# 用 Python 创建具有列表理解的词典

> 原文:[https://www . geesforgeks . org/用 python 创建一个包含列表理解的词典/](https://www.geeksforgeeks.org/create-a-dictionary-with-list-comprehension-in-python/)

在本文中，我们将讨论如何用 Python 中的[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)来创建字典。

## 方法 1:使用 dict()方法

使用 dict()方法，我们可以将列表理解转换为字典。这里我们将像元组值列表一样传递 list _ understance，这样第一个值在字典中充当关键字，第二个值在字典中充当值。

> **语法:**dict(list _ understance)

**例 1** : Python 程序创建学生列表理解并转换成字典。

## 蟒蛇 3

```py
# create a list comprehension with student age
data = [('sravan', 23), ('ojaswi', 15),
        ('rohith', 8), ('gnanesh', 4), ('bobby', 20)]

# using dict method
dict(data)
```

**输出:**

```py
{'bobby': 20, 'gnanesh': 4, 'ojaswi': 15, 'rohith': 8, 'sravan': 23}
```

我们还可以在 dict()方法中对循环使用以下内容。

> **语法** : dict([(键，值)表示键，数据中的值])

**例 2** :

## 蟒蛇 3

```py
# create a list comprehension with student age
data = [('sravan', 23), ('ojaswi', 15),
        ('rohith', 8), ('gnanesh', 4), ('bobby', 20)]

# using dict method inside for loop
dict([(key, value) for key, value in data])
```

**输出:**

```py
{'bobby': 20, 'gnanesh': 4, 'ojaswi': 15, 'rohith': 8, 'sravan': 23}
```

## 方法二:使用 [zip()](https://www.geeksforgeeks.org/zip-in-python/) 配合 dict()方法

在这个方法中，我们将创建两个列表，这样第一个列表中的值将是关键字，第二个列表中的值将是字典中的值。

> **语法** : dict(zip(key_list，value_list))

**例 1** :

## 蟒蛇 3

```py
# create a list with student name
name = ['sravan', 'ojaswi', 'rohith', 'gnanesh', 'bobby']

# create a list with student age
age = [23, 21, 32, 11, 23]

# using dict method with zip()
dict(zip(name, age))
```

**输出**:

```py
{'bobby': 23, 'gnanesh': 11, 'ojaswi': 21, 'rohith': 32, 'sravan': 23}
```

## 方法 3:使用 Iterable

在这里，我们可以使用 iterable for loop 在给定的日期上迭代。

> **语法**:{键:数据中(键，值)的值}

**例**:

## 蟒蛇 3

```py
# create a list comprehension with student age
data = [('sravan', 23), ('ojaswi', 15),
        ('rohith', 8), ('gnanesh', 4), ('bobby', 20)]

# display using iterable method
{key: value for (key, value) in data}
```

**输出:**

```py
{'bobby': 20, 'gnanesh': 4, 'ojaswi': 15, 'rohith': 8, 'sravan': 23}
```

## 方法 4:添加过滤器

我们可以在列表理解的条目中添加一个过滤器，只为基于条件的特定数据创建一个字典。过滤是指根据条件向字典中添加值。

> **语法**:{键:数据条件中(键，值)的值}

**例**:

## 蟒蛇 3

```py
# create a list comprehension with student age
data = [('sravan', 23), ('ojaswi', 15),
        ('rohith', 8), ('gnanesh', 4), ('bobby', 20)]

# create a dictionary with list
# comprehension if value is equal to 20
print({key: value for (key, value) in data if value == 20})

# create a dictionary with list
# comprehension if value is greater than  to 10
print({key: value for (key, value) in data if value > 10})

# create a dictionary with list
# comprehension if key is sravan
print({key: value for (key, value) in data if key == 'sravan'})
```

**输出:**

```py
{'bobby': 20}
{'sravan': 23, 'ojaswi': 15, 'bobby': 20}
{'sravan': 23}
```