# Python–将字典列表转换为列表字典

> 原文:[https://www . geesforgeks . org/python-convert-list-of-dictionary-to-list/](https://www.geeksforgeeks.org/python-convert-list-of-dictionaries-to-dictionary-of-lists/)

在本文中，我们将讨论如何将字典列表转换为列表字典。

## 方法 1:用于循环

通过基于第一个关键字的迭代，我们可以将 dict 列表转换为 dict 列表。Python 程序创建学生字典列表

## 蟒蛇 3

```py
# create a list of dictionaries
# with student data
data = [
    {'name': 'sravan', 'subjects': ['java', 'python']},
    {'name': 'bobby', 'subjects': ['c/cpp', 'java']},
    {'name': 'ojsawi', 'subjects': ['iot', 'cloud']},
    {'name': 'rohith', 'subjects': ['php', 'os']},
    {'name': 'gnanesh', 'subjects': ['html', 'sql']}

]

# display
data
```

**输出:**

```py
[{'name': 'sravan', 'subjects': ['java', 'python']},
 {'name': 'bobby', 'subjects': ['c/cpp', 'java']},
 {'name': 'ojsawi', 'subjects': ['iot', 'cloud']},
 {'name': 'rohith', 'subjects': ['php', 'os']},
 {'name': 'gnanesh', 'subjects': ['html', 'sql']}]
```

**示例:**将字典列表转换为列表字典

## 蟒蛇 3

```py
# create an empty dictionary
dictionary_of_list = {}

# for loop to convert list of dict
# to dict of list
for item in data:
    name = item['name']
    dictionary_of_list[name] = item

# display
dictionary_of_list
```

**输出:**

```py
{'bobby': {'name': 'bobby', 'subjects': ['c/cpp', 'java']},
 'gnanesh': {'name': 'gnanesh', 'subjects': ['html', 'sql']},
 'ojsawi': {'name': 'ojsawi', 'subjects': ['iot', 'cloud']},
 'rohith': {'name': 'rohith', 'subjects': ['php', 'os']},
 'sravan': {'name': 'sravan', 'subjects': ['java', 'python']}}
```

## 方法二:使用[词典理解](https://www.geeksforgeeks.org/python-dictionary-comprehension/)

这里我们使用字典理解将字典列表转换为列表的字典，因此我们根据新字典中的键将列表作为值传递

> **语法**:{键:[I[键]代表列表中的 I _ of _ dictionary]代表列表中的键[0]}
> 
> **其中**
> 
> *   字典列表是输入
> *   关键字是字典列表中的关键字

**示例:**将字典的学生列表转换为列表的字典的程序

## 蟒蛇 3

```py
# consider the list of dictionary
data = [{'manoj': 'java', 'bobby': 'python'},
        {'manoj': 'php', 'bobby': 'java'},
        {'manoj': 'cloud', 'bobby': 'big-data'}]

# convert into dictionary of list
# with list as values
print({key: [i[key] for i in data] for key in data[0]})
```

**输出:**

```py
{'manoj': ['java', 'php', 'cloud'], 'bobby': ['python', 'java', 'big-data']}
```

## 方法三:使用[熊猫数据框](https://www.geeksforgeeks.org/python-pandas-dataframe/)

通过使用熊猫数据帧，我们将把字典表转换成字典表

> **句法**:熊猫。DataFrame(字典列表)。to_dict(orient="list ")
> 
> **其中:**
> 
> *   字典列表是输入
> *   to_dict()方法是转换成字典
> *   定向参数是转换成列表

**例**:

## 蟒蛇 3

```py
#import pandas
import pandas as pd

# consider the list of dictionary
data = [{'manoj': 'java', 'bobby': 'python'},
        {'manoj': 'php', 'bobby': 'java'},
        {'manoj': 'cloud', 'bobby': 'big-data'}]

# convert into dictionary of list
# with list as values using pandas dataframe
pd.DataFrame(data).to_dict(orient="list")
```

**输出**:

> {'bobby': ['python '，' java '，'大数据']，' manoj': ['java '，' php '，' cloud']}

## 方法 4:使用 NumPy

Numpy 用于处理数组，我们可以通过使用键或索引来获取值

## 蟒蛇 3

```py
# import numpy module
import numpy as np

# create numpy data
data = np.array([(10, 20), (50, 60)],
                dtype=[('value1', int), 
                       ('value2', int)])

# display by using index
print(data[0])

# display by uing key
print(data['value1'])
```

**输出:**

```py
(10, 20)
[10 50]
```