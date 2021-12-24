# Python——如何迭代嵌套字典？

> 原文:[https://www . geesforgeks . org/python-如何迭代嵌套字典/](https://www.geeksforgeeks.org/python-how-to-iterate-over-nested-dictionary/)

在本文中，我们将讨论如何在 Python 中迭代嵌套字典。

嵌套字典意味着字典中的字典，我们将看到迭代这种数据结构的所有可能方式。

正在使用的嵌套词典:

> { '学生 1': { '姓名':' Bobby '，' Id': 1，'年龄':20}，
> 
> 学生 2': { '姓名':' ojaswi '，' Id': 2，'年龄':22}，
> 
> 学生 3:“{ '姓名':' rohith '，' Id': 3，'年龄':20}}

为此，我们将使用 For 循环遍历字典，以获取嵌套字典的所有键值。

**语法:**

```py
for i in dictionary_name:
     print(dictionary_name[i])
```

在哪里

*   dictionary_name 是输入词典
*   dictionary_name[i]是获取词典的值

**示例**:从字典中获取嵌套字典的 Python 程序

## 蟒蛇 3

```py
# create a nested dictionary with 3 
# fields of 3 students
data = {
    'Student 1': {'Name': 'Bobby', 'Id': 1, "Age": 20},
    'Student 2': {'Name': 'ojaswi', 'Id': 2, "Age": 22},
    'Student 3': {'Name': 'rohith', 'Id': 3, "Age": 20},
}

# iterate all the nested dictionaries with 
# both keys and values
for i in data:

    # display
    print(data[i])
```

**输出:**

```py
{'Name': 'Bobby', 'Id': 1, 'Age': 20}
{'Name': 'ojaswi', 'Id': 2, 'Age': 22}
{'Name': 'rohith', 'Id': 3, 'Age': 20}
```

如果这是需求所要求的，也可以只获取键或值。同样，对于这种情况，for 循环的使用略有不同。

为每次迭代从嵌套字典中获取键，调用 key()函数。

**语法:**

```py
data[i].keys()
```

**示例:**从嵌套字典中获取关键字的 Python 程序

## 蟒蛇 3

```py
# create a nested dictionary with 3 fields of 3 students
data = {
    'Student 1': {'Name': 'Bobby', 'Id': 1, "Age": 20},
    'Student 2': {'Name': 'ojaswi', 'Id': 2, "Age": 22},
    'Student 3': {'Name': 'rohith', 'Id': 3, "Age": 20},
}

# iterate all the nested dictionaries with keys
for i in data:
  # display
    print(data[i].keys())
```

**输出:**

```py
dict_values(['Bobby', 1, 20])
dict_values(['ojaswi', 2, 22])
dict_values(['rohith', 3, 20])
```

与获取值类似，在每次迭代后，values()函数用于完成任务。

**语法:**

```py
data[i].values()
```

**示例:**从嵌套字典中获取值的 Python 程序

## 蟒蛇 3

```py
# create a nested dictionary with 3 fields of 3 students
data = {
    'Student 1': {'Name': 'Bobby', 'Id': 1, "Age": 20},
    'Student 2': {'Name': 'ojaswi', 'Id': 2, "Age": 22},
    'Student 3': {'Name': 'rohith', 'Id': 3, "Age": 20},
}

# iterate all the nested dictionaries with values
for i in data:
  # display
    print(data[i].values())
```

**输出:**

```py
dict_values(['Bobby', 1, 20])
dict_values(['ojaswi', 2, 22])
dict_values(['rohith', 3, 20])
```