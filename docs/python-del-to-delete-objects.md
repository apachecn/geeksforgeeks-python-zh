# Python del 删除对象

> 原文:[https://www.geeksforgeeks.org/python-del-to-delete-objects/](https://www.geeksforgeeks.org/python-del-to-delete-objects/)

python 中的 **`del`** 关键字主要用于删除 Python 中的对象。由于 python 中的所有内容都以这样或那样的方式表示一个对象，因此`del`关键字也可以用于删除列表、分割列表、删除字典、从字典中移除键值对、删除变量等。

```py
 Syntax: del object_name
```

以下是显示 `del`关键字的各种用例的各种示例:

**1。删除对象的 del 关键字**

**示例:**
在下面的程序中我们将使用 `del Sample_class` 语句删除 Sample_class。

```py
class Sample_class:
    some_variable = 20

    # method of the class
    def my_method(self):
        print("GeeksForGeeks")

# check if class exists
print(Sample_class)

# delete the class using del keyword
del Sample_class

# check if class exists
print(Sample_class)
```

**输出:**

```py
class '__main__.Sample_class'
```

```py
NameError:name 'Sample_class' is not defined
```

**1。删除变量的 del 关键字**

**示例:**
在下面的程序中，我们将使用 `del`关键字删除一个变量。

```py
my_variable1 = 20
my_variable2 = "GeeksForGeeks"

# check if my_variable1 and my_variable2 exists
print(my_variable1)
print(my_variable2)

# delete both the variables
del my_variable1
del my_variable2

# check if my_variable1 and my_variable2 exists
print(my_variable1)
print(my_variable2)
```

**输出:**

```py
20
GeeksForGeeks
20
```

```py
NameError: name 'my_variable2' is not defined
```

**1。删除列表和列表切片的 del 关键字**

**示例:**
在下面的程序中，我们将使用 `del`关键字删除一个列表并切片另一个列表。

```py
my_list1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
my_list2 =["Geeks", "For", "Geek"]

# check if my_list1 and my_list2 exists
print(my_list1)
print(my_list2)

# delete second element of my_list1
del my_list1[1]

# check if the second element in my_list1 is deleted
print(my_list1)

# slice my_list1 from index 3 to 5
del my_list1[3:5]

# check if the elements from index 3 to 5 in my_list1 is deleted
print(my_list1)

# delete my_list2
del my_list2

# check if my_list2 exists
print(my_list2)
```

**输出:**

```py
[1, 2, 3, 4, 5, 6, 7, 8, 9]
['Geeks', 'For', 'Geek']
[1, 3, 4, 5, 6, 7, 8, 9]
[1, 3, 4, 7, 8, 9]
```

```py
NameError: name 'my_list2' is not defined
```

**1。删除字典和删除键值对的 del 关键字**

**示例:**
在下面的程序中，我们将删除一个字典，并使用 `del`关键字删除几个键值对。

```py
my_dict1 = {"small": "big", "black": "white", "up": "down"}
my_dict2 = {"dark": "light", "fat": "thin", "sky": "land"}

# check if my_dict1 and my_dict2 exists
print(my_dict1)
print(my_dict2)

# delete key-value pair with key "black" from my_dict1
del my_dict1["black"]

# check if the  key-value pair with key "black" from my_dict1 is deleted
print(my_dict1)

# delete my_dict2
del my_dict2

# check if my_dict2 exists
print(my_dict2)
```

**输出:**

```py
{'small': 'big', 'black': 'white', 'up': 'down'}
{'dark': 'light', 'fat': 'thin', 'sky': 'land'}
{'small': 'big', 'up': 'down'}
```

```py
NameError: name 'my_dict2' is not defined
```

详见 [delattr()和 del()](http://delattr() and del() in Python) 。