# 如何在 Python 中执行 COUNTIF 函数？

> 原文:[https://www . geeksforgeeks . org/如何在 python 中执行一个 countif 函数/](https://www.geeksforgeeks.org/how-to-perform-a-countif-function-in-python/)

在本文中，我们将讨论如何在 Python 中执行 COUNTIF 函数。

## **COUNTIF**

如果条件满足，我们使用这个函数来计数元素。请注意，该单词代表 **COUNT + IF。**这意味着如果所提供的条件得到满足，我们就要对元素进行计数。

**接近**

*   我们将有一个带有一些列的数据框。
*   我们将使用函数**求和()。****sum()**函数将取一个**可迭代的**值。我们将有一个包含元素列表的数据框。然后我们将传递条件来检查当前元素是否满足它。
*   sum() **返回**一个**整数**值。所以我们将存储该值并将其打印出来。

**语法**

sum()函数的语法如下。

```
sum(data-list condition)
```

让我们举一个例子，我们有一个名为 myList 的列表，列表中有整数值。我们希望大于等于 40 的项目数。所以我们可以使用求和函数如下，

```
sum(mylist >= 40)
```

对于使用两个条件，我们可以使用 AND( &)或 OR( |)来分隔这两个条件。

```
sum((myList) >= 40 & (myList <= 90)) # AND
sum((myList) >= 40 | (myList <= 90)) # OR
```

## 方法 1:使用单个列

首先，让我们**创建**一个**数据框**。这里有**两列**，分别是**视图**和**喜欢**。我们将保持每列**长度**与**相同**。

## 蟒 3

```
# create a dictionary
my_data = {"views": [12, 13, 100, 80, 91],
           "likes": [3, 8, 23, 17, 56]}

# convert to dataframe
my_df = pd.DataFrame(my_data)
```

### 条件 1:如果视图超过 30 个

我们将使用 **sum()** 功能检查在**视图列表**列中，**值**是否大于 30。然后求和功能将**计数****行**，其对应的**视图大于**30。

## 蟒 3

```
import pandas as pd

# Data
my_data = {"views": [12, 13, 100, 80, 91], 
           "likes": [3, 8, 23, 17, 56]}
my_df = pd.DataFrame(my_data)

# Printing the DataFrame
print(my_df.to_string())

# Printing the number of views greater
# than 30
print("View greater than 30: ",
      sum(my_df.views > 30))
```