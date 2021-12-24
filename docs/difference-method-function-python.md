# Python 中方法和函数的区别

> 原文:[https://www . geesforgeks . org/difference-method-function-python/](https://www.geeksforgeeks.org/difference-method-function-python/)

在这里，**解释 Python 中方法和函数的关键区别**。Java 也是一种面向对象的语言，但是其中没有函数的概念。但是 Python 同时有方法和函数的概念。

**Python 方法**

1.  方法按其名称调用，但它与对象相关联(依赖)。
2.  一个方法是**隐式传递给调用它的对象**。
3.  它**可以返回也可以不返回任何数据。**
4.  方法**可以对相应类**包含的数据(实例变量)进行操作

**Python 中的基本方法结构:**

```
# Basic Python method 
class class_name
    def method_name () :
        ......
        # method body
        ......   
```

**Python 3 自定义方法:**

```
# Python 3  User-Defined  Method
class ABC :
    def method_abc (self):
        print("I am in method_abc of ABC class. ")

class_ref = ABC() # object of ABC class
class_ref.method_abc()
```

输出:

```
 I am in method_abc of ABC class
```

**Python 3 内置方法:**

```
import math

ceil_val = math.ceil(15.25)
print( "Ceiling value of 15.25 is : ", ceil_val) 
```

输出:

```
Ceiling value of 15.25 is :  16
```

了解更多 [Python 天花板()和地板()方法](https://www.geeksforgeeks.org/floor-ceil-function-python/)。

**功能**

1.  函数是一个代码块，它的名字也叫做**。(独立)**
2.  **函数可以有不同的参数，也可以没有任何参数。如果**有任何数据(参数)**通过，则为**明确通过**。**
3.  **它**可以返回也可以不返回任何数据。****
4.  **函数不处理类及其实例概念。**

****Python 中的基本功能结构:****

```
def function_name ( arg1, arg2, ...) :
    ......
    # function body
    ......   
```

 ****Python 3 自定义函数:****

```
def Subtract (a, b):
    return (a-b)

print( Subtract(10, 12) ) # prints -2

print( Subtract(15, 6) ) # prints 9
```

**输出:**

```
-2
9 
```

****Python 3 内置函数:****

```
s = sum([5, 15, 2])
print( s ) # prints 22

mx = max(15, 6)
print( mx ) # prints 15
```

**输出:**

```
22
15 
```

**了解更多 [Python sum()函数](https://www.geeksforgeeks.org/sum-function-python/)。更多了解 [Python min()或 max()函数](https://www.geeksforgeeks.org/max-min-python/)。**

****方法和功能的区别****

1.  **简单地说，函数和方法看起来都很相似，因为它们以几乎相似的方式执行，但关键的区别是“**类及其对象**的概念。**
2.  **函数只能通过名称来调用**，因为它是独立定义的。但是方法 c **不能仅仅用它的名字**来调用，我们需要通过引用定义它的类来调用这个类，也就是说，方法是在一个类中定义的，因此它们依赖于这个类。****