# 在 Python 中访问属性和方法

> 原文:[https://www . geesforgeks . org/access-attributes-methods-python/](https://www.geeksforgeeks.org/accessing-attributes-methods-python/)

类的属性是定义其实例的相应方法的函数对象。它们用于实现类的访问控制。
也可以使用以下内置方法和函数访问类的属性:

1.  **getattr()–**该功能用于访问对象的属性。
2.  **hasat tr()–**该功能用于检查属性是否存在。
3.  **setattr()–**该功能用于设置属性。如果该属性不存在，则会创建它。
4.  **delattr()–**此功能用于删除属性。如果您在删除属性后访问该属性，则会引发错误“类没有属性”。

以下方法用下面给出的例子来解释:

```
# Python code for accessing attributes of class 
class emp: 
    name='Harsh'
    salary='25000'
    def show(self): 
        print (self.name) 
        print (self.salary) 
e1 = emp() 
# Use getattr instead of e1.name 
print (getattr(e1,'name')) 

# returns true if object has attribute 
print (hasattr(e1,'name')) 

# sets an attribute 
setattr(e1,'height',152) 

# returns the value of attribute name height 
print (getattr(e1,'height')) 

# delete the attribute 
delattr(emp,'salary') 
```

输出:

```
Harsh
True
152
```

**静态方法:**静态方法是完全不使用自变量 self 的方法[成员函数]。若要声明静态方法，请使用语句“@staticmethod”继续。

```
# Python code for accessing methods using static method 
class test: 
    @staticmethod
    def square(x): 
        test.result = x*x 

# object 1 for class 
t1=test() 

# object 2 for class 
t2 = test() 
t1.square(2) 

# printing result for square(2) 
print (t1.result) 
t2.square(3) 

# printing result for square(3) 
print (t2.result) 

# printing the last value of result as we declared the method static 
print (t1.result) 
```

输出:

```
4
9
9
```

**在另一个类中访问一个类的属性和方法**

通过将一个类的对象传递给另一个类来访问另一个类的属性和方法。
用下面给出的例子解释:

```
# Python code for Accessing attributes and methods 
# of one class in another class 

class ClassA(): 
    def __init__(self): 
        self.var1 = 1
        self.var2 = 2

    def methodA(self): 
        self.var1 = self.var1 + self.var2 
        return self.var1 

class ClassB(ClassA): 
    def __init__(self, class_a): 
        self.var1 = class_a.var1 
        self.var2 = class_a.var2 

object1 = ClassA() 
# updates the value of var1 
summ = object1.methodA() 

# return the value of var1 
print (summ) 

# passes object of classA 
object2 = ClassB(object1) 

# return the values carried by var1,var2 
print( object2.var1)
print (object2.var2) 
```

输出:

```
3
3
2
```