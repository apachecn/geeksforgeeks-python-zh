# 获取 Python 中字典的长度

> 原文:[https://www . geesforgeks . org/get-length-in-dictionary-python/](https://www.geeksforgeeks.org/get-length-of-dictionary-in-python/)

Python 中的字典是数据的键值对的集合。这些在 python 中的许多操作中都有使用，并且是 Python 中最重要的数据结构之一。计算字典的长度，使用内置的`len()`方法。

#### Python 中的 len()方法:

这个内置方法以一个 Python 对象作为参数，并返回其中的项数。它可以用于字符串、列表、字典、元组和集合。唯一需要注意的是参数必须是序列或集合。

**查找简单字典的长度:**

考虑一个人的以下细节:

```
Name:Steve
Age:30
Designation:Programmer
```

这个信息可以用简单的字典来表示。一个简单的字典只包含一些键值对。它们并不复杂。应用`len()`方法时，直接给出答案。它给出了字典中条目的数量。例如:

```
# Python program to find 
# length of the dictionary

# a simple dictionary
dict1 ={'Name':'Steve', 'Age':30, 'Designation':'Programmer'}

# using len() counts the
# number of entries
print("len() method :", len(dict1))

# using dict.keys() counts
# the no.of.keys in dictionary
print("len() method with keys() :", len(dict1.keys()))

# using dict.values() counts
# the no.of.valuess in dictionary
print("len() method with values():", len(dict1.values()))
```

**输出:**

```
len() method : 3
len() method with keys() : 3
len() method with values(): 3
```

**查找嵌套词典的长度:**

考虑一个人的以下细节:

```
Name:Steve
Age:30
Designation:Programmer
address:
      Street:Brigade  Road
      City:Bangalore
      Country:India
```

这种信息可以用嵌套字典来表示。嵌套词典包含词典中的词典。在键值对中，对于一个键，另一个字典可以是该值。在这种情况下，如果将字典简单地传递给`len()`方法，输出将是不正确的。请看下面的代码:

```
# Python program to find 
# length of the nested dictionary

# A nested dictionary
dict2 ={ # outer dictionary
       'Name':'Steve',
       'Age':30,
       'Designation':'Programmer',
       'address':{# inner dictionary
           'Street':'Brigade Road',
           'City':'Bangalore',
           'Country':'India'

                 }
      }

print("len() method :", len(dict2))
print("len() method with keys() :", len(dict2.keys()))
print("len() method with values():", len(dict2.values()))
```

**输出:**

```
len() method : 4
len() method with keys() : 4
len() method with values(): 4

```

在这里，无论你使用哪种方法，你只会得到“4”作为输出。但实际的条目数是‘7’。关键是姓名、年龄、名称、地址、街道、城市和国家。该方法将作为其中一个键的值的内部字典视为单个值。为了克服这个问题，我们需要显式地将内部字典的长度添加到外部字典中。它可以编码如下:

```
# Python program to find the
# length of the nested dictionary

# A nested dictionary

dict2 ={                   
       'Name':'Steve',
       'Age':30,
       'Designation':'Programmer',
       'address':
              {
           'Street':'Brigade Road',
           'City':'Bangalore',
           'Country':'India'
              }
      }

# total length = length of outer dict +
# length of inner dict
length = len(dict2)+len(dict2['address'])

print("The length of the nested dictionary is ", length)
```

**输出:**

```
The length of the nested dictionary is  7

```

现在它工作正常！！！

**但是，有没有可能明确编程，每次增加内部字典的长度？**如果我们事先不知道有多少本内部词典呢？现在考虑以下细节:

```
Name:
    first name:Steve
    last name:Jobs
Age:30
Designation:Programmer
address:
      Street:Brigade  Road
      City:Bangalore
      Country:India
```

这里我们有两本内部词典。每次显式增加内部字典的长度并不是一种优化的方法。我们可以把`isinstance()`和`len()`方法结合起来解决这个问题。

**isinstance()方法:**

这个方法需要两个参数。第一个是**对象**。我们需要传递一个 Python 对象给它。该对象可以是 int、float、iterable 或任何其他对象。要传递的第二个参数是**类型/类**。它表示针对其实例检查第一个参数的类型/类。这个方法可以帮助我们找到嵌套字典的长度。

这个想法是首先将整个字典的长度存储在一个变量*(这里说“长度”)*中。然后遍历字典的所有`values()`，检查是否是`dict`的实例。如果 *`'True'`* ，则找到该内部字典的长度，并将其添加到变量 *`length`* 中。这样就可以找到嵌套字典的总长度。下面给出了示例代码。

```
# Python program to find
# length of nested dictionary

# nested dictionary
dict2 ={
       'Name':
           {
               'first_name':'Steve',
               'Last_name':'Jobs'
           },
       'Age':30,
       'Designation':'Programmer',
       'address':
           {
           'Street':'Rockins Road',
           'City':'Bangalore',
           'Country':'India'
           }       
      }

# storing the outer dictionary length 
length = len(dict2)

# iterating to find the length
#  of all inner dictionaries
for i in dict2.values():

    # checking whether the value is a dictionary
    if isinstance(i, dict):
        length += len(i)

print("The length of the dictionary is", length)
```

**输出:**

```
The length of the dictionary is  9

```

如果字典的嵌套更深，如下所示:

```
Name:
    first name:Steve
    last name:Jobs
Age:30
Designation:Programmer
address:
      Street:
          St_number:4
          St_name:Brigade  Road
      City:Bangalore
      Country:India
```

然后修改下面给出的代码:

```
# Python program to find 
# length of nested dictionary

# nested dictionary
dict2 ={
       'Name':
           {
               'first_name':'Steve',
               'Last_name':'Jobs'
           },
       'Age':30,
       'Designation':'Programmer',
       'address':
           {
           'Street':
               {
                   'st_number':4,
                   'st_name':'Rockins Road'
               },
           'City':'Bangalore',
           'Country':'India'
           }       
      }

# storing the outer dictionary length 
length = len(dict2)

# iterating to find the length 
# of all inner dictionaries
for i in dict2.values():

    # checking whether the value is a dictionary
    if isinstance(i, dict):

        # add the length of inner dictionary
        length += len(i)

        # check whether th inner dictionary
        # is further nested
        for j in i.values():

             if isinstance(j, dict):
                length += len(j)

print("The total length of the dictionary is ", length)
```

**输出:**

```
The total length of the dictionary is  11

```