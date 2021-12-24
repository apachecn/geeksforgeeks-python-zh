# Python–获取元组列表中的第一个元素

> 原文:[https://www . geesforgeks . org/python-获取元组列表中的第一个元素/](https://www.geeksforgeeks.org/python-get-first-element-in-list-of-tuples/)

在这篇文章中。我们将讨论如何在 Python 中获取元组列表中的第一个元素。

**创建一个** **元组列表并显示:**

## 蟒蛇 3

```py
# create tuples with college
# id and name and store in a list
data=[(1,'sravan'), (2,'ojaswi'),
      (3,'bobby'), (4,'rohith'),
      (5,'gnanesh')]

# display data
print(data)
```

**输出:**

> [(1，' sravan '，(2，' ojaswi ')，(3，' bobby ')，(4，' rohith '，(5，' gnanesh')]

## **方法一:使用迭代(** [**为循环**](https://www.geeksforgeeks.org/python-for-loops/) **)**

我们可以遍历整个元组列表，并通过使用索引获得第一个，index-0 将给出列表中每个元组的第一个元素。

> **语法:**对于 _of_tuple 列表中的 var:
> 
> 打印(var[0])

**示例:**这里我们将从元组列表中获取第一个 IE 学生证。

## 蟒蛇 3

```py
# create tuples with college id
# and name and store in a list
data = [(1,'sravan'), (2,'ojaswi'),
        (3,'bobby'),(4,'rohith'),
        (5,'gnanesh')]

# iterate using for loop
# to access first elements
for i in data:
   print(i[0])
```

**输出:**

```py
1
2
3
4
5
```

## **方法二:使用** [**zip 功能**](https://www.geeksforgeeks.org/zip-in-python/)

Zip 用于组合两个或多个数据/数据结构。这里我们可以使用 zip()函数，通过使用索引作为 0 来获取第一个元素。

> **语法:**列表(zip(*data))[0]

**示例:**访问元组列表中第一个元素的 Python 代码。

## 蟒蛇 3

```py
# create tuples with college id
# and name and store in a list
data = [(1,'sravan'),(2,'ojaswi'),
        (3,'bobby'),(4,'rohith'),
        (5,'gnanesh')]

# get first element using zip
print(list(zip(*data))[0])
```

**输出:**

```py
(1, 2, 3, 4, 5)
```

## **方法三:用地图配合**[**item getter()**](https://www.geeksforgeeks.org/ways-sort-list-dictionaries-values-python-using-itemgetter/)**方法**

这里我们使用 map 函数和 itemgetter()方法来获取第一个元素，这里我们也使用 index–0 来获取第一个元素。itemgetter()方法在运算符模块中可用，因此我们需要导入运算符

> **语法:**映射(operator.itemgetter(0)，数据)

**示例:** Python 程序访问第一个元素。

## 蟒蛇 3

```py
import operator

# create tuples with college id
# and name and store in a list
data = [(1,'sravan'),(2,'ojaswi'),
        (3,'bobby'),(4,'rohith'),
        (5,'gnanesh')]

# map the data using item
# getter method with first elements
first_data = map(operator.itemgetter(0), data)

# display first elements
for i in first_data:
    print(i)
```

**输出:**

```py
1
2
3
4
5
```

## **方法四:用** [**映射()**](https://www.geeksforgeeks.org/python-map-function/) **用**[**λ表达**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

这里我们使用 lambda 表达式和 map()函数，这里我们也使用索引 0 来获取第一个数据。

> **语法:**映射(λx:x[0]，数据)
> 
> **在哪里，**
> 
> *   x 是获取第一个元素的迭代器
> *   数据是元组列表数据

**示例:**访问第一个元素的 Python 代码。

## 蟒蛇 3

```py
# create tuples with college id
# and name and store in a list
data=[(1,'sravan'),(2,'ojaswi'),
      (3,'bobby'),(4,'rohith'),
      (5,'gnanesh')]

# map with lambda expression to get first element
first_data = map(lambda x: x[0], data)

# display data
for i in first_data:
    print(i)
```

**输出:**

```py
1
2
3
4
5
```