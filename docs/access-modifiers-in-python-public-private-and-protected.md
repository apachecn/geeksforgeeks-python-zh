# Python 中的访问修饰符:公共、私有和受保护

> 原文:[https://www . geesforgeks . org/access-modifiers-in-python-public-private-and-protected/](https://www.geeksforgeeks.org/access-modifiers-in-python-public-private-and-protected/)

**先决条件:**Python 中的[下划线(_)](https://www.geeksforgeeks.org/underscore-_-python/)、[Python 中的](https://www.geeksforgeeks.org/private-variables-python/)私有变量

各种面向对象的语言，如 C++、Java、Python 控制访问修改，用于限制对类的变量和方法的访问。大多数编程语言都有三种形式的访问修饰符，分别是类中的 **Public** 、 **Protected** 和 **Private** 。
Python 使用“_”符号来确定特定数据成员或类的成员函数的访问控制。Python 中的访问说明符在保护数据免受未经授权的访问和防止数据被利用方面发挥着重要作用。
Python 中的类有三种类型的访问修饰符:

*   **公共访问修改器**
*   **受保护访问修饰符**
*   **私有访问修饰符**

## 公共访问修饰符:

声明为公共的类成员很容易从程序的任何部分访问。默认情况下，类的所有数据成员和成员函数都是公共的。

## 蟒蛇 3

```
# program to illustrate public access modifier in a class

class Geek:

     # constructor
     def __init__(self, name, age):

           # public data members
           self.geekName = name
           self.geekAge = age

     # public member function     
     def displayAge(self):

           # accessing public data member
           print("Age: ", self.geekAge)

# creating object of the class
obj = Geek("R2J", 20)

# accessing public data member
print("Name: ", obj.geekName)

# calling public member function of the class
obj.displayAge()
```

**Output:** 

```
Name:  R2J
Age:  20
```

在上面的程序中，geekName 和 geekAge 是公共数据成员，displayAge()方法是 Geek 类的公共成员函数。极客类的这些数据成员可以从程序的任何地方访问。

## 受保护的访问修饰符:

声明为受保护的类的成员只能由从该类派生的类访问。通过在类的数据成员前添加一个下划线“_”符号，可以声明该类的数据成员受到保护。

## 蟒蛇 3

```
# program to illustrate protected access modifier in a class

# super class
class Student:

     # protected data members
     _name = None
     _roll = None
     _branch = None

     # constructor
     def __init__(self, name, roll, branch): 
          self._name = name
          self._roll = roll
          self._branch = branch

     # protected member function  
     def _displayRollAndBranch(self):

          # accessing protected data members
          print("Roll: ", self._roll)
          print("Branch: ", self._branch)

# derived class
class Geek(Student):

       # constructor
       def __init__(self, name, roll, branch):
                Student.__init__(self, name, roll, branch)

       # public member function
       def displayDetails(self):

                 # accessing protected data members of super class
                print("Name: ", self._name)

                 # accessing protected member functions of super class
                self._displayRollAndBranch()

# creating objects of the derived class       
obj = Geek("R2J", 1706256, "Information Technology")

# calling public member functions of the class
obj.displayDetails()
```

**Output:** 

```
Name:  R2J
Roll:  1706256
Branch:  Information Technology
```

在上面的程序中，_name、_roll 和 _branch 是受保护的数据成员，_displayRollAndBranch()方法是超级类 Student 的受保护方法。displayDetails()方法是从 Student 类派生的类 Geek 的公共成员函数，Geek 类中的 displayDetails()方法访问 Student 类的受保护数据成员。

## 私有访问修饰符:

声明为私有的类成员只能在类中访问，私有访问修饰符是最安全的访问修饰符。类的数据成员通过在该类的数据成员前添加双下划线“__”符号来声明为私有。

## 蟒蛇 3

```
# program to illustrate private access modifier in a class

class Geek:

     # private members
     __name = None
     __roll = None
     __branch = None

     # constructor
     def __init__(self, name, roll, branch): 
          self.__name = name
          self.__roll = roll
          self.__branch = branch

     # private member function 
     def __displayDetails(self):

           # accessing private data members
           print("Name: ", self.__name)
           print("Roll: ", self.__roll)
           print("Branch: ", self.__branch)

     # public member function
     def accessPrivateFunction(self):

           # accesing private member function
           self.__displayDetails() 

# creating object   
obj = Geek("R2J", 1706256, "Information Technology")

# calling public member function of the class
obj.accessPrivateFunction()
```

**Output:** 

```
Name:  R2J
Roll:  1706256
Branch:  Information Technology
```

在上面的程序中，__name，__roll 和 __branch 是私有成员，__displayDetails()方法是私有成员函数(这些只能在类内访问)，accessPrivateFunction()方法是类 Geek 的公共成员函数，可以从程序内的任何地方访问。accessPrivateFunction()方法访问 Geek 类的私有成员。

**下面是一个程序，说明 Python 中一个类的所有上述三个访问修饰符(公共、受保护的**、**和私有)的使用:**

## 蟒蛇 3

```
# program to illustrate access modifiers of a class

# super class
class Super:

     # public data member
     var1 = None

     # protected data member
     _var2 = None

     # private data member
     __var3 = None

     # constructor
     def __init__(self, var1, var2, var3): 
          self.var1 = var1
          self._var2 = var2
          self.__var3 = var3

    # public member function  
     def displayPublicMembers(self):

          # accessing public data members
          print("Public Data Member: ", self.var1)

     # protected member function  
     def _displayProtectedMembers(self):

          # accessing protected data members
          print("Protected Data Member: ", self._var2)

     # private member function  
     def __displayPrivateMembers(self):

          # accessing private data members
          print("Private Data Member: ", self.__var3)

     # public member function
     def accessPrivateMembers(self):    

          # accessing private member function
          self.__displayPrivateMembers()

# derived class
class Sub(Super):

      # constructor
       def __init__(self, var1, var2, var3):
                Super.__init__(self, var1, var2, var3)

      # public member function
       def accessProtectedMembers(self):

                # accessing protected member functions of super class
                self._displayProtectedMembers()

# creating objects of the derived class    
obj = Sub("Geeks", 4, "Geeks !")

# calling public member functions of the class
obj.displayPublicMembers()
obj.accessProtectedMembers()
obj.accessPrivateMembers()

# Object can access protected member
print("Object is accessing protected member:", obj._var2)

# object can not access private member, so it will generate Attribute error
#print(obj.__var3)
```

**Output:** 

```
Public Data Member:  Geeks
Protected Data Member:  4
Private Data Member:  Geeks !
```

在上面的程序中，accessProtectedMembers()方法是类 *Sub* 的公共成员函数，访问类 Super 的受保护成员函数 _ displayProtectedMembers()方法，而 accessPrivateMembers()方法是类 Super 的公共成员函数，访问类 Super 的私有成员函数 __displayPrivateMembers()方法。