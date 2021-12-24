# Python 中的实例方法

> 原文:[https://www.geeksforgeeks.org/instance-method-in-python/](https://www.geeksforgeeks.org/instance-method-in-python/)

类是用户定义的蓝图或原型，从中创建对象。类提供了一种将数据和功能捆绑在一起的方法。创建一个新类会创建一个新类型的对象，从而允许创建该类型的新实例。每个类实例都可以附加属性来维护其状态。类实例也可以有方法(由其类定义)来修改其状态。

**示例:**

```
# Python program to demonstrate
# classes  

class Person:  

    # init method or constructor   
    def __init__(self, name):  
        self.name = name  

    # Sample Method   
    def say_hi(self):  
        print('Hello, my name is', self.name)  

p = Person('Nikhil')  
p.say_hi() 
```

**输出:**

```
Hello, my name is Nikhil

```

**注意:**更多信息请参考 [Python 类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/)

#### 实例方法

实例属性是那些不被对象共享的属性。每个对象都有自己的实例属性副本。

例如，考虑一类有许多对象的形状，如圆形、正方形、三角形等。有自己的属性和方法。实例属性指的是特定对象的属性，比如三角形的边是 3，而正方形的边可以是 4。

实例方法可以访问甚至修改实例的属性值。它有一个默认参数:-

*   **[self](https://www.geeksforgeeks.org/self-in-python-class/)–**这是一个指向当前传递实例的关键字。但是它不需要在每次调用实例方法时都被传递。

**示例:**

```
# Python program to demonstrate
# instance methods

class shape:

    # Calling Constructor
    def __init__(self, edge, color):
        self.edge = edge
        self.color = color

    # Instance Method
    def finEdges(self):
        return self.edge

    # Instance Method
    def modifyEdges(self, newedge):
        self.edge = newedge

# Driver Code
circle = shape(0, 'red')
square = shape(4, 'blue')

# Calling Instance Method
print("No. of edges for circle: "+ str(circle.finEdges()))

# Calling Instance Method
square.modifyEdges(6)

print("No. of edges for square: "+ str(square.finEdges()))
```

**输出**

```
No. of edges for circle: 0
No. of edges for square: 6
```