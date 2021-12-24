# Python 中的继承|第 2 集

> 原文:[https://www.geeksforgeeks.org/inheritance-in-python-set-2/](https://www.geeksforgeeks.org/inheritance-in-python-set-2/)

先决条件:[Python 中的继承基础](https://www.geeksforgeeks.org/inheritance-in-python/)、[继承、对象、issubclass 和 super 的示例](https://www.geeksforgeeks.org/oop-in-python-set-3-inheritance-examples-of-object-issubclass-and-super/)

Python 中有 2 个与继承相关的内置函数。它们是:

**1。isinstance():** 它检查对象的类型。它的语法是:
isinstance(object_name，class_name)
如果 object_name 的类是 class_name else **则返回**True**False**。
例如:

```py
# Python code to demonstrate issubclass()

print(isinstance(5, int))
```

**Output:**

```py
True

```

上面的代码将显示以下输出:
**真**
这是因为 5 是一个整数，因此属于 int 类。
**注:**“int”在 Python 中既是类型又是类。

**2。issubclass():** 它检查一个特定的类是否是另一个类的子类。它的语法是:
issubclass(childclass_name，parentclass_name)
它将返回 **True** 如果输入的子类实际上是从输入的父类 else 派生的，它将返回 **False** 。
例如:

```py
# Python code to demonstrate issubclass()
class A():
      def __init__(self, a):
            self.a = a
class B(A):
      def __init__(self, a, b):
            self.b = b
            A.__init__(self, a)

print(issubclass(B, A))
```

**Output:**

```py
True

```

上面的代码将显示以下输出:
**真**

**<u>多重继承:</u>**
当一个类从多个父类继承时，称为多重继承。它的工作方式与单一继承相同。

```py
# Python code to demonstrate multiple inheritance

# first parent class
class Person(object):                  
      def __init__(self, name, idnumber):
            self.name = name
            self.idnumber = idnumber

# second parent class      
class Employee(object):                
      def __init__(self, salary, post):
            self.salary = salary
            self.post = post

# inheritance from both the parent classes      
class Leader(Person, Employee):        
      def __init__(self, name, idnumber, salary, post, points):
            self.points = points
            Person.__init__(self, name, idnumber)
            Employee.__init__(self, salary, post)   
```

**Output:**

创建类的实例时，请确保您向函数提供参数的顺序与该类的块中的顺序相关。例如，在上面的代码中，如果我们必须生成一个实例，我们将编写

```py
ins = Leader('Rahul', 882016, 75000, 'Assistant Manager', 560)
```

如果你把序列位置 75000 和“助理经理”互换，代码将把“助理经理”作为工资，75000 作为职位。
自己看吧。

```py
# first parent class
class Person(object):                 
      def __init__(self, name, idnumber):
            self.name = name
            self.idnumber = idnumber

# second parent class      
class Employee(object):                
      def __init__(self, salary, post):
            self.salary = salary
            self.post = post

# inheritance from both the parent classes      
class Leader(Person, Employee):        
      def __init__(self, name, idnumber, salary, post, points):
            self.points = points
            Person.__init__(self, name, idnumber)
            Employee.__init__(self, salary, post)
            print(self.salary)

ins = Leader('Rahul', 882016, 'Assistant Manager', 75000, 560)
```

**Output:**

```py
Assistant Manager

```

**<u>覆盖方法:</u>**
覆盖一个方法意味着在子类中重新定义一个已经在其他类中定义过的方法。
子类中的方法只有在超类中存在另一个具有相同名称和相同参数集的方法时才会被调用为被覆盖。
同样，我们不能覆盖超类的私有方法，也就是名字前有双下划线的方法。
例如:

```py
# Base Class
class A(object):                
        def __init__(self):
                constant1 = 1
        def method1(self):
                print('method1 of class A')

class B(A):
        def __init__(self):
                constant2 = 2
                self.calling1()
                A. __init__(self)
        def method1(self):
                print('method1 of class B')
        def calling1(self):
                self.method1()
                A.method1(self)
b = B()
```

**Output:**

```py
method1 of class B
method1 of class A

```

该代码调用 B 类的方法 1，而不是 A 类，因为 Python 按照从下到上的顺序搜索函数。
如果要调用 A 类的 method1，将 self.method1()替换为 A.method1(self)。
上述重写方法的过程适用于旧式类，也就是父类没有从“对象”类继承的类。
对于新样式的类，其中父类继承自内置的“对象”类，有另一个重写方法的过程。
super()方法帮助我们在新的样式类中重写方法。其语法如下:
**super(class_name，instance_)of_class)。override _ method _ name()**
让我们假设有 3 个类 A、B 和 c，这 3 个类都有一个被称为‘method 1’的公共函数。super()的工作来了。

```py
class A(object):
        def function1(self):
                print 'function of class A'
class B(A):
        def function1(self):
                print 'function of class B'
                super(B, self).function1()
class C(B):
        def function1(self):
                print 'function of class C'
                super(C, self).function1()
j = C()
j.function1()
```

**Output:**

```py
function of class C
function of class B
function of class A

```

超级函数中的“self”参数充当父类的对象，因此调用父类的函数 1。