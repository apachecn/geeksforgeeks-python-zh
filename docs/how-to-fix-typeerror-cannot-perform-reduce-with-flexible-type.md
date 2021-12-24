# 如何修复:类型错误:无法用灵活类型

进行约简

> 原文:[https://www . geesforgeks . org/如何修复类型错误-无法执行-使用灵活类型减少/](https://www.geeksforgeeks.org/how-to-fix-typeerror-cannot-perform-reduce-with-flexible-type/)

在本文中，我们将讨论 TypeError:不能用灵活类型执行 reduce，以及如何修复它。当我们找到由多种类型的数据组成的二维 NumPy 数组的平均值时，可能会出现这种错误。

**使用中的数据集:**

<figure class="table">

| 

**学生证**

 | 

**学生姓名**

 | 

**分支**

 | 

**标记**

 |
| --- | --- | --- | --- |
| One hundred and one | （英、瑞）哈里（人名） | 中学生毕业考试 | Eighty-seven |
| One hundred and two | 留宿（remain overnight 的缩写） | 欧洲经济委员会 | Eighty-eight |
| One hundred and three | 阿莱夏 | 中学生毕业考试 | seventy-two |

</figure>

当我们使用 NumPy 创建这个表时，这个 2D 数组由多种类型的数据组成。在这里，我们有字符串和整数数据类型。要找到任何像 Marks 这样的数字列的平均值，它会抛出 TypeError，因为它不知道当不是所有的值都是数字时如何取平均值(即学生姓名，分支由类型字符串的数据组成)。

**示例:**产生错误代码

## 蟒蛇 3

```
# import necessary packages
import numpy as np

# create a 2D Array
students = np.array([['Student ID', 'Student Name', 'Branch', 'Marks'],
                     [101, 'Hary', 'CSE', 87],
                     [102, 'Ron', 'ECE', 88],
                     [103, 'Alexa', 'CSE', 72]])

# mean of marks(3rd column)
print(students[:, 3].mean())
```