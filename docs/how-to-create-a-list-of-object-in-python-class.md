# 如何在 Python 类中创建对象列表

> 原文:[https://www . geesforgeks . org/如何创建 python 类对象列表/](https://www.geeksforgeeks.org/how-to-create-a-list-of-object-in-python-class/)

我们可以通过在**列表**中添加类**实例**来创建 Python 中的对象列表。这样，列表中的每个索引都可以指向类的实例属性和方法，并且可以访问它们。如果仔细观察，对象列表的行为就像 c 语言中的结构数组。让我们借助示例来更好地理解它。

**示例#1:**

```py
# Python3 code here creating class
class geeks: 
    def __init__(self, name, roll): 
        self.name = name 
        self.roll = roll

# creating list       
list = [] 

# appending instances to list 
list.append( geeks('Akash', 2) )
list.append( geeks('Deependra', 40) )
list.append( geeks('Reaper', 44) )

for obj in list:
    print( obj.name, obj.roll, sep =' ' )

# We can also access instances attributes
# as list[0].name, list[0].roll and so on.
```

**输出:**

```py
Akash 2
Deependra 40
Reaper 44

```