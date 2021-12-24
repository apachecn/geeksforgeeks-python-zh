# 如何将 dict.get()与多维 dict 一起使用？

> 原文:[https://www . geeksforgeeks . org/如何使用-dict-get-with-多维-dict/](https://www.geeksforgeeks.org/how-to-use-dict-get-with-multidimensional-dict/)

**如果关键字在字典中，python 中的 get()方法会返回关键字的值。如果关键字不在字典中，则返回无。它还接受另一个可选参数，即在字典中找不到关键字时将返回的值。**

> ****语法:** dict.get(key，value)**

这里，键是一个必选参数，它是一个我们想从字典中获取值的键。And value 是一个可选字段，它是在字典中找不到指定键时返回的值。值的默认值为“无”。

### 例 1:

## 蟒蛇 3

```
# single dimension dictionary
d = {'jhon': 22, 'sanie': 34, 'munk': 19}

# return value if found if not then return Not found
print(d.get('sanie', 'Not found'))
```

**输出:**

```
34
```

### 例 2:

现在，让我们看看如何在多维字典中使用 dict.get()。对于多维字典，我们使用。在单个语句中多次 get()。

T2T4

```
# Example of dict.get() with multidimensional dict
dict = {'India': {'captain': 'Virat', 'Batsman': 'Rohit', 
                  'Bolwer': 'Bumrah'},
        'England': {'captain': 'Root', 'Batsman': 'Buttler',
                    'Bolwer': 'anderson'},
        'Australia': {'captain': 'Paine', 'Batsman': 'Warner',
                      'Bolwer': 'Starck'},
        'Pakistan': {'captain': 'Babar', 'Batsman': 'Hafiz',
                     'Bolwer': 'Aamir'},
        'West Indies': {'captain': 'Pollard', 'Batsman': 'Gayle',
                        'Bolwer': 'Narayan'}
        }

# find batsman for india
# return Not Found if not exists in dict
print(dict.get('India').get('Batsman', 'Not Found'))
```

T5

**输出:**

```
Rohit
```

### **例 3:**

你可以看到它给出了正确的输出。让我们理解这个 dict.get()的工作原理。First dict.get()返回字典中关键字“India”的所有值。它返回{'captain':'Virat '，' Batsman':'Rohit '，' Bolwer':'Bumrah'}现在对于这个字典我们再次使用 get()方法确实找到了值。所以对于《蝙蝠侠》来说，它重演了《罗希特》。

T2T4

```
# Example of dict.get() with multidimensional dict
dict = {'India': {'captain': 'Virat', 'Batsman': 'Rohit', 
                  'Bolwer': 'Bumrah'},
        'England': {'captain': 'Root', 'Batsman': 'Buttler',
                    'Bolwer': 'anderson'},
        'Australia': {'captain': 'Paine',
                      'Batsman': 'Warner', 'Bolwer': 'Starck'},
        'Pakistan': {'captain': 'Babar', 'Batsman': 'Hafiz', 
                     'Bolwer': 'Aamir'},
        'West Indies': {'captain': 'Pollard', 'Batsman': 'Gayle', 
                        'Bolwer': 'Narayan'}
        }

# find fielder for india
# return Not Found if not exists in dict
print(dict.get('India').get('Fielder', 'Not Found'))
```

T5

**输出:**

```
Not Found
```

### **例 4:**

你可以看到菲尔德不存在于由“印度”返回的字典中。这就是为什么它给出“未找到”作为输出。但是使用 get()方法有一个问题。如果没有找到对应于第一个键的值，那么它将返回一个字符串，第二个 get()方法将应用于该字符串。这将给出一个错误，因为 dict.get()是字典的方法，而不是字符串的方法。

T2T4

```
# Example of dict.get() with multidimensional dict
dict = {'India': {'captain': 'Virat', 'Batsman': 'Rohit',
                  'Bolwer': 'Bumrah'},
        'England': {'captain': 'Root', 'Batsman': 'Buttler', 
                    'Bolwer': 'anderson'},
        'Australia': {'captain': 'Paine', 'Batsman': 'Warner', 
                      'Bolwer': 'Starck'},
        'Pakistan': {'captain': 'Babar', 'Batsman': 'Hafiz',
                     'Bolwer': 'Aamir'},
        'West Indies': {'captain': 'Pollard', 'Batsman': 'Gayle',
                        'Bolwer': 'Narayan'}
        }

# find batsman for new zealand
# return Not Found if not exists in dict
# if new zealand not found in dict will result in error
print(dict.get('new zealand').get('Batsman', 'Not Found'))
```

T5

**输出:**

```
Traceback (most recent call last):
  File "/home/4deb2392dee0ab15dec836bca68a69e2.py", line 12, in <module>
    print(dict.get('new zealand').get('Batsman', 'Not Found'))
AttributeError: 'NoneType' object has no attribute 'get'
```

这给出了“NoneType”对象错误，因为字符串数据类型没有名为 get()的方法。因此，为了解决这个错误，我们将使用 get()方法的第二个参数，如果在字典中找不到键，则该参数用于默认输出。如果字典中不存在关键字，我们将返回一个空字典。

T2T4

```
# Example of dict.get() with multidimensional dict
dict = {'India': {'captain': 'Virat', 'Batsman': 'Rohit', 
                  'Bolwer': 'Bumrah'},
        'England': {'captain': 'Root', 'Batsman': 'Buttler',
                    'Bolwer': 'anderson'},
        'Australia': {'captain': 'Paine', 'Batsman': 'Warner',
                      'Bolwer': 'Starck'},
        'Pakistan': {'captain': 'Babar', 'Batsman': 'Hafiz',
                     'Bolwer': 'Aamir'},
        'West Indies': {'captain': 'Pollard', 'Batsman': 'Gayle',
                        'Bolwer': 'Narayan'}
        }

# find batsman for new zealand
# return Not Found if not exists in dict
print(dict.get('new zealand',{}).get('Batsman', 'Not Found'))
```

T5

**输出:**

```
Not Found
```

在输出中，您可以看到即使在字典中找不到第一个键，这也能很好地工作。我们也将对更高维度使用相同的方法。现在让我们看看我们是否能把它用于更高的维度。

T2T4

```
# use of dict.get() in multidimensional dictionary

dict = {'emp1': {'Name': {'First Name': 'Joe', 
                          'Last Name': 'tribiani'}, 
                 'age': 32},
        'emp2': {'Name': {'First Name': 'Mark',
                          'Last Name': 'Adam'},
                 'age': 20},
        'emp3': {'Name': {'First Name': 'luci', 
                          'Last Name': 'truk'},
                 'age': 47},
        }

# return Not Found if emp2 is not found
# or Name is not Found or Last name is not found
print(dict.get('emp2', {}).get('Name', {}).get('Last Name',
                                               'Not Found'))
```

T5

**输出:**

```
Adam
```

所以这非常有效。我们可以在任何维度上使用它。如果在字典中找不到关键字，只需添加字典作为默认返回值。添加字典作为默认返回值，除了最后一个 get()方法，否则它将输出一个空字典。如果找不到值，请在最后一个 get()方法中添加要显示的任何字符串。