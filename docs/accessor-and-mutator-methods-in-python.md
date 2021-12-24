# Python 中的访问器和变异器方法

> 原文:[https://www . geesforgeks . org/python 中的存取器和变异器方法/](https://www.geeksforgeeks.org/accessor-and-mutator-methods-in-python/)

在 Python 中，[类](https://www.geeksforgeeks.org/python-classes-and-objects/)是用户定义类型的对象原型。它指定和定义相同类型的对象，一个类包括一组数据和方法定义。此外，一个对象是一个类的单个实例，但是您可以从一个类创建多个对象。
**注:**更多信息，请参考 [Python 类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/)

## 存取器和变异器方法

因此，你们都必须知道，对象的内部数据必须保密。但是类接口中应该有一些方法可以允许对象的用户以平静的方式访问和更改数据(存储在内部)。因此，在这种情况下，我们有两种方法，即*访问器*和*变异器*，分别有助于访问和更改内部存储的数据。

*   **访问器方法:**该方法用于访问对象的状态，即隐藏在对象中的数据可以通过该方法访问。但是，这个方法不能改变对象的状态，它只能访问隐藏的数据。我们可以用*获得*这个词来命名这些方法。

*   **Mutator 方法:**该方法用于对对象的状态进行变异/修改，即改变数据变量的隐藏值。它可以立即将变量值设置为新值。此方法也称为更新方法。而且，我们可以用*集*这个词来命名这些方法。

**以下示例说明了 Python 中** ***取值器和变异器*** **方法的使用:**
**示例 1:**

## 计算机编程语言

```py
# Python program to illustrate the use of
# Accessor and Mutator methods

# importing "array" for array operations
import array

# initializing array with array values
# initializes array with signed integers
arr = array.array('i', [5, 1, 3, 4, 2, 2, 7])

# Accesses the index of the value in argument
print (arr.index(2))

# Accesses the number of time the
# stated value is present
print (arr.count(2))

# Mutates the array list
(arr.append(19))

# Prints the array after alteration
print (arr)
```

**Output:** 

```py
4
2
array('i', [5, 1, 3, 4, 2, 2, 7, 19])
```

因此，这里的 *index()* 和 *count()* 方法只访问数据，所以它们是访问器方法，但是这里的 *append()* 方法修改了数组，所以它是一个 mutator 方法。
**例 2:**

## 计算机编程语言

```py
# Python program to illustrate the use of
# Accessor and Mutator methods

# Defining class Car
class Car:

    # Defining method init method with a parameter
    def __init__(self, carname):
        self.__make = carname

    # Defining Mutator Method
    def set_make(self, carname):
        self.__make = carname

    # Defining Accessor Method
    def get_make(self):
        return self.__make

# Creating an object
myCar = Car('Ford');

# Accesses the value of the variable
# using Accessor method and then
# prints it
print (myCar.get_make())

# Modifying the value of the variable
# using Mutator method
myCar.set_make('Porche')

# Prints the modified value
print (myCar.get_make())
```

**Output:** 

```py
Ford
Porche
```

因此，这里的汽车名称是使用访问器方法访问的，即 **get_make** ，然后使用 Mutator 方法修改，即 **set_make** 。