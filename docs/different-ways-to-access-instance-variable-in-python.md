# Python 中访问实例变量的不同方式

> 原文:[https://www . geesforgeks . org/不同的访问方式-python 中的实例变量/](https://www.geeksforgeeks.org/different-ways-to-access-instance-variable-in-python/)

**实例属性**是那些不被对象共享的属性。每个对象都有自己的实例属性副本，即对于每个对象，实例属性都是不同的。

**访问类的实例变量有两种方式:**

*   在类内通过使用[自我](https://www.geeksforgeeks.org/self-in-python-class/)和对象引用。
*   使用`[getattr()](http://hello my name is: HARRY my roll number is: 1001 HARRY)`方法

**示例 1:** 使用自身和对象引用

```py
#creating class
class student:

    # constructor
    def __init__(self, name, rollno):

        # instance variable
        self.name = name
        self.rollno = rollno

    def display(self):

        # using self to access 
        # variable inside class
        print("hello my name is:", self.name)
        print("my roll number is:", self.rollno)

# Driver Code
# object created
s = student('HARRY', 1001)

# function call through object
s.display()

# accessing variable from 
# outside the class
print(s.name)
```

**输出:**

```py
hello my name is: HARRY
my roll number is: 1001
HARRY
```

**示例 2:** 使用 getattr()

```py
# Python code for accessing attributes of class 
class emp: 
    name='Harsh'
    salary='25000'
    def show(self): 
        print(self.name)
        print(self.salary)

# Driver Code
e1 = emp() 
# Use getattr instead of e1.name 
print(getattr(e1,'name'))

# returns true if object has attribute 
print(hasattr(e1,'name'))

# sets an  attribute  
setattr(e1,'height',152) 

# returns the value of attribute name height 
print(getattr(e1,'height'))

# delete the attribute 
delattr(emp,'salary') 
```

**输出:**

```py
Harsh
True
152
```