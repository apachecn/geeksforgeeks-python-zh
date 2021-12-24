# 在 Python 中将字典附加到列表中

> 原文:[https://www . geesforgeks . org/将字典追加到 python 列表中/](https://www.geeksforgeeks.org/appending-a-dictionary-to-a-list-in-python/)

在本文中，我们将讨论如何在 Python 中将字典追加到列表数据结构中。

**这里我们将讨论:**

1.  将字典附加到具有相同关键字和不同值的列表
2.  使用 append()方法
3.  使用 copy()方法使用 append()方法列出
4.  使用 deepcopy()方法使用 append()方法列出
5.  使用 NumPy。

## **方法 1:用** **相同的键和不同的值**将字典追加到列表中

在这里，我们将使用 for 循环将整数类型的字典追加到一个空列表中，该循环具有相同的键但具有不同的值。我们将使用使用 [zip()](https://www.geeksforgeeks.org/zip-in-python/) 功能

> **语法:** list=[dict(zip([key]，[x])，范围为 x(开始，停止)]
> 
> 其中，key 是键，range()是要追加的值的范围

**示例:** Python 代码，添加 100 个从 1 到 100 的值，其中 1 是列表的键

在本例中，我们将从 1 到 100 的元素作为值，并将这些值赋给键 1，最后，我们将元素进行压缩，最后，我们将元素追加到列表中。

## 蟒蛇 3

```
# append 100 values from 1 to 100
# with 1 as key to list
l = [dict(zip([1],[x])) for x in range(1,100)]

# display list
print(l)
```

**输出:**

> [{1: 1}, {1: 2}, {1: 3}, {1: 4}, {1: 5}, {1: 6}, {1: 7}, {1: 8}, {1: 9}, {1: 10}, {1: 11}, {1: 12}, {1: 13}, {1: 14}, {1: 15}, {1: 16}, {1: 17}, {1: 18}, {1: 19}, {1: 20}, {1: 21}, {1: 22}, {1: 23}, {1: 24}, {1: 25}, {1: 26}, {1: 27}, {1: 28}, {1: 29}, {1: 30}, {1: 31}, {1: 32}, {1: 33}, {1: 34}, {1: 35}, {1: 36}, {1: 37}, {1: 38}, {1: 39}, {1: 40}, {1: 41}, {1: 42}, {1: 43}, {1: 44}, {1: 45}, {1: 46}, {1: 47}, {1: 48}, {1: 49}, {1: 50}, {1: 51}, {1: 52}, {1: 53}, {1: 54}, {1: 55}, {1: 56}, {1: 57}, {1: 58}, {1: 59}, {1: 60}, {1: 61}, {1: 62}, {1: 63}, {1: 64}, {1: 65}, {1: 66}, {1: 67}, {1: 68}, {1: 69}, {1: 70}, {1: 71}, {1: 72}, {1: 73}, {1: 74}, {1: 75}, {1: 76}, {1: 77}, {1: 78}, {1: 79}, {1: 80}, {1: 81}, {1: 82}, {1: 83}, {1: 84}, {1: 85}, {1: 86}, {1: 87}, {1: 88}, {1: 89}, {1: 90}, {1: 91}, {1: 92}, {1: 93}, {1: 94}, {1: 95}, {1: 96}, {1: 97}, {1: 98}, {1: 99}]

## **方法二:使用** [**追加()**](https://www.geeksforgeeks.org/append-extend-python/) **方法**

这里，我们将使用 append()方法将字典追加到列表中，该方法用于在列表中追加一个项目。

> **语法:** list.append(字典)
> 
> **在哪里，**
> 
> *   列表是输入列表
> *   字典是要追加的输入字典

**示例 1:** 向空列表追加字典的 Python 代码

在这里，我们将学生 id 视为关键字，将姓名视为字典的值，因此我们使用追加方法将学生字典追加到空列表中

## 蟒蛇 3

```
# create an empty list
l = []

# create a dictionary wih student details
student = {7058:'sravan kumsr Gottumukkala',
           7059:'ojaswi',7060:'bobby',
           7061:'gnanesh',7062:'rohith'}

# append this dictionary to the empty list
l.append(student)

# display list
l
```

**输出:**

```
[{7058: 'sravan kumsr Gottumukkala',
 7059: 'ojaswi',
 7060: 'bobby',
 7061: 'gnanesh',
 7062: 'rohith'}]
```

**示例 2:** 在包含元素的列表中添加字典

在这里，我们将学生证视为关键字，将姓名视为字典的值。因此，我们使用 append 方法将已经包含一些元素的列表追加到学生词典中

## 蟒蛇 3

```
# create an list that contain some elements
l = [1, 2, "hi", "welcome"]

# create a dictionary wih student details
student={7058:'sravan kumsr Gottumukkala',
         7059:'ojaswi',7060:'bobby',
         7061:'gnanesh',7062:'rohith'}

# append this dictionary to the empty list
l.append(student)

# display list
l
```

**输出:**

```
[1,
2,
'hi',
'welcome',
{7058: 'sravan kumsr Gottumukkala',
 7059: 'ojaswi',
 7060: 'bobby',
 7061: 'gnanesh',
 7062: 'rohith'}]
```

## **方法三:使用** [复制()](https://www.geeksforgeeks.org/python-dictionary-copy/) **并追加()方法**

这里，我们将使用 append()方法将字典追加到列表中，我们可以使用 copy()来追加到列表中

> **语法:**字典. copy()

**示例 1:** 使用 copy()方法将字典追加到空列表的 Python 代码

这里我们将学生 id 视为关键字，将姓名视为字典的值，因此我们使用复制方法将学生字典追加到使用追加方法的空列表中

## 蟒蛇 3

```
# create an empty list
l = []

# create a dictionary wih student details
student = {7058:'sravan kumsr Gottumukkala',
           7059:'ojaswi',7060:'bobby',
           7061:'gnanesh',7062:'rohith'}

# append this dictionary to the
# empty list using copy() method
l.append(student.copy())

# display list
l
```

**输出:**

```
[{7058: 'sravan kumsr Gottumukkala',
 7059: 'ojaswi',
 7060: 'bobby',
 7061: 'gnanesh',
 7062: 'rohith'}]
```

**示例 2:** 使用 copy()方法追加字典以列出包含元素的字典

在这里，我们将学生 id 视为关键字，将名称视为字典的值，因此我们使用 copy 方法将学生字典附加到已经包含使用 append 方法的元素的列表中

## 蟒蛇 3

```
# create an list that contain some elements
l = [1, 2, "hi", "welcome"]

# create a dictionary wih student details
student = {7058:'sravan kumsr Gottumukkala',
           7059:'ojaswi',7060:'bobby',
           7061:'gnanesh',7062:'rohith'}

# append this dictionary to
# the empty list using copy() method
l.append(student.copy())

# display list
l
```

**输出:**

```
[1,
2,
'hi',
'welcome',
{7058: 'sravan kumsr Gottumukkala',
 7059: 'ojaswi',
 7060: 'bobby',
 7061: 'gnanesh',
 7062: 'rohith'}]
```

## **方法 4:使用 deepcopy()方法和 append()方法**

深度复制是一个递归发生复制过程的过程，这里我们将通过深度复制字典来将字典追加到列表中。

> **语法:**追加(deepcopy())

**示例 1:** 使用深度复制将字典追加到列表中

在这里，我们将学生 id 视为关键字，将姓名视为字典的值，因此我们使用深度复制方法将学生字典追加到使用追加方法的空列表中

## 蟒蛇 3

```
# import deepcopy module
from copy import deepcopy

# create an empty list
l = []

# create a dictionary wih student details
student = {7058: 'sravan kumsr Gottumukkala',
           7059: 'ojaswi', 7060: 'bobby',
           7061: 'gnanesh', 7062: 'rohith'}

# append this dictionary to
# the empty list using deepcopy() method
l.append(deepcopy(student))

# display list
l
```

**输出:**

```
[{7058: 'sravan kumsr Gottumukkala',
 7059: 'ojaswi',
 7060: 'bobby',
 7061: 'gnanesh',
 7062: 'rohith'}]
```

**示例 2:** 将字典追加到包含元素的列表中

在这里，我们将学生 id 视为关键字，将名称视为字典的值，因此我们使用 deepcopy 方法将学生字典附加到已经包含使用 append 方法的元素的列表中

## 计算机编程语言

```
# import deepcopy module
from copy import deepcopy

# create an list that contain some elements
l = [1, 2, "hi", "welcome"]

# create a dictionary wih student details
student = {7058:'sravan kumsr Gottumukkala',
           7059:'ojaswi',7060:'bobby',
           7061:'gnanesh',7062:'rohith'}

# append this dictionary to the empty
# list using deepcopy() method
l.append(deepcopy(student))

# display list
l
```

**输出:**

```
[1,
2,
'hi',
'welcome',
{7058: 'sravan kumsr Gottumukkala',
 7059: 'ojaswi',
 7060: 'bobby',
 7061: 'gnanesh',
 7062: 'rohith'}]
```

## **方法五:使用 Numpy**

[Numpy](https://www.geeksforgeeks.org/numpy-in-python-set-1-introduction/) 代表用于存储和处理数组的数字 python，这里我们将使用 Numpy 来追加字典。

> **语法:** np.append(res_array，{'key': "value"})。tolist()
> 
> ***在哪里，***
> 
> *   res_array 是 resultabt 数组
> *   追加用于追加到数组
> *   tolist()用于转换列表

**示例:**使用 NumPy 方法将字典追加到列表中的 Python 代码。

在这里，我们创建了一个包含主题的元素列表，传递 GFG 键并将其附加到列表中

## 蟒蛇 3

```
# import numpy library 
import numpy as np

# define a list
subjects = ["PHP", "Java", "SQL"]

# iterating the elements in
# list to create an numpy array
data = np.array([{'GFG': i} for i in subjects])

# append to the numpy array to list
final = np.append(res_array, {'GFG': "ML/DL"}).tolist()

# Printing the appended data
print(final)
```

**输出:**

> [{ ' gfg ':PHP ' }，{ ' gfg ':Java ' }，{ gfg:SQL ' }，{ gfg:ml/dl ' }]