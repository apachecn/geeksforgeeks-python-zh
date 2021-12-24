# Python 中的枚举

> 原文:[https://www.geeksforgeeks.org/enum-in-python/](https://www.geeksforgeeks.org/enum-in-python/)

Python 中的枚举是使用名为“**枚举**的模块实现的。枚举使用**类**创建。枚举有**名称和与之相关的值**。
**枚举属性:**
**1。**枚举可以显示为**字符串**或 [repr](https://www.geeksforgeeks.org/str-vs-repr-in-python/) 。
**2。**可以使用 **type()** 检查枚举的类型。
T22】3。”**name**关键字用于显示枚举成员的名称。

## 计算机编程语言

```py
# Python code to demonstrate enumerations

# importing enum for enumerations
import enum

# creating enumerations using class
class Animal(enum.Enum):
    dog = 1
    cat = 2
    lion = 3

# printing enum member as string
print ("The string representation of enum member is : ",end="")
print (Animal.dog)

# printing enum member as repr
print ("The repr representation of enum member is : ",end="")
print (repr(Animal.dog))

# printing the type of enum member using type()
print ("The type of enum member is : ",end ="")
print (type(Animal.dog))

# printing name of enum member using "name" keyword
print ("The name of enum member is : ",end ="")
print (Animal.dog.name)
```

输出:

```py
The string representation of enum member is : Animal.dog
The repr representation of enum member is : <Animal.dog: 1>
The type of enum member is : <enum 'Animal'>
The name of enum member is : dog
```

**4。**枚举是**可迭代的**。它们可以使用循环
**5 进行迭代。**枚举支持**哈希**。枚举可用于[词典](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)或[集合](https://www.geeksforgeeks.org/sets-in-python/)。

## 计算机编程语言

```py
# Python code to demonstrate enumerations
# iterations and hashing
# importing enum for enumerations
import enum

# creating enumerations using class
class Animal(enum.Enum):
    dog = 1
    cat = 2
    lion = 3

# printing all enum members using loop
print ("All the enum values are : ")
for Anim in (Animal):
    print(Anim)

# Hashing enum member as dictionary
di = {}
di[Animal.dog] = 'bark'
di[Animal.lion] = 'roar'

# checking if enum values are hashed successfully
if di=={Animal.dog : 'bark',Animal.lion : 'roar'}:
      print ("Enum is hashed")
else: print ("Enum is not hashed")
```

输出:

```py
All the enum values are : 
Animal.dog
Animal.cat
Animal.lion
Enum is hashed
```

**访问模式:**枚举成员有两种访问方式
**1。通过值** :-在这个方法中，枚举成员的值被传递。
**2。通过名称** :-在这个方法中，枚举成员的名称被传递。
单独的值或名称也可以使用“**名称**”或“**值**关键字访问。
**比较:**枚举支持两种类型的比较
**1。身份** :-这些是用关键字**是**、**不是**检查的。
**2。相等** :-相等比较“ **==** ”和“**！=** "也支持类型。

## 计算机编程语言

```py
# Python code to demonstrate enumerations
# Access and comparison

# importing enum for enumerations
import enum

# creating enumerations using class
class Animal(enum.Enum):
    dog = 1
    cat = 2
    lion = 3

# Accessing enum member using value
print ("The enum member associated with value 2 is : ",end="")
print (Animal(2))

# Accessing enum member using name 
print ("The enum member associated with name lion is : ",end="")
print (Animal['lion'])

# Assigning enum member
mem = Animal.dog

# Displaying value
print ("The value associated with dog is : ",end="")
print (mem.value)

# Displaying name 
print ("The name associated with dog is : ",end="")
print (mem.name)

# Comparison using "is"
if Animal.dog is Animal.cat:
       print ("Dog and cat are same animals")
else : print ("Dog and cat are different animals")

# Comparison using "!="
if Animal.lion != Animal.cat:
       print ("Lions and cat are different")
else : print ("Lions and cat are same")
```

输出:

```py
The enum member associated with value 2 is : Animal.cat
The enum member associated with name lion is : Animal.lion
The value associated with dog is : 1
The name associated with dog is : dog
Dog and cat are different animals
Lions and cat are different
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。