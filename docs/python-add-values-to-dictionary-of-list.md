# Python–将值添加到列表字典中

> 原文:[https://www . geeksforgeeks . org/python-将值添加到列表词典/](https://www.geeksforgeeks.org/python-add-values-to-dictionary-of-list/)

在本文中，我们将讨论如何向列表字典添加值。

我们可以通过使用列表向字典添加值，输入列表将是以下结构:

```
[('key',value),...........,('key',value)]
```

所以上面的列表是一个输入，我们可以使用 for 循环将值添加到列表字典中。

> **语法**:
> 
> 对于键，输入值:
> 
> 数据[密钥]。追加(值)
> 
> **在哪里，**
> 
> *   键是输入列表中的键
> *   值是输入列表中的值

**示例 1:** Python 程序创建学生科目的输入列表并添加到列表字典中

## 蟒蛇 3

```
# import defaultdict module
from collections import defaultdict

# declare a list with student data
input = [('bhanu', 'html'),
         ('bhanu', 'php'),
         ('suma', 'python'),
         ('rasmi', 'java'),
         ('suma', 'html/csscss')]

# declare a default dict
data = defaultdict(list)

# append to the dictionary
for key, value in input:
    data[key].append(value)

# display
print(data.items())
```

**输出:**

> dict_items([('bhanu '，['html '，' php'])，(' suma '，['python '，' html/CSS '])，(' rasmi '，['java'])])

**例 2:**

## 蟒蛇 3

```
# import defaultdict module
from collections import defaultdict

# declare a list with student data with age
input = [('bhanu', 10), ('uma', 12), ('suma', 11)]

# declare a default dict
data = defaultdict(list)

# append to the dictionary
for key, value in input:
    data[key].append(value)

# display
print(data.items())
```

**输出:**

```
dict_items([('bhanu', [10]), ('uma', [12]), ('suma', [11])])
```