# Python 中的多态性

> 原文:[https://www.geeksforgeeks.org/polymorphism-in-python/](https://www.geeksforgeeks.org/polymorphism-in-python/)

**什么是多态性:**多态性这个词的意思是有多种形式。在编程中，多态性意味着相同的函数名(但是不同的签名)用于不同的类型。
**内置多态函数示例:**

## 蟒蛇 3

```
# Python program to demonstrate in-built poly-
# morphic functions

# len() being used for a string
print(len("geeks"))

# len() being used for a list
print(len([10, 20, 30]))
```

**Output:** 

```
5
3
```

**用户定义的多态函数示例:**

## 蟒蛇 3

```
# A simple Python function to demonstrate
# Polymorphism

def add(x, y, z = 0):
    return x + y+z

# Driver code
print(add(2, 3))
print(add(2, 3, 4))
```

**Output:** 

```
5
9
```

**类方法的多态性:**
下面的代码展示了 Python 如何以同样的方式使用两种不同的类类型。我们创建一个 for 循环，循环遍历一组对象。然后调用方法，而不考虑每个对象是哪种类型的类。我们假设这些方法实际上存在于每个类中。

## 蟒蛇 3

```
class India():
    def capital(self):
        print("New Delhi is the capital of India.")

    def language(self):
        print("Hindi is the most widely spoken language of India.")

    def type(self):
        print("India is a developing country.")

class USA():
    def capital(self):
        print("Washington, D.C. is the capital of USA.")

    def language(self):
        print("English is the primary language of USA.")

    def type(self):
        print("USA is a developed country.")

obj_ind = India()
obj_usa = USA()
for country in (obj_ind, obj_usa):
    country.capital()
    country.language()
    country.type()
```

**Output:** 

```
New Delhi is the capital of India.
Hindi is the most widely spoken language of India.
India is a developing country.
Washington, D.C. is the capital of USA.
English is the primary language of USA.
USA is a developed country.
```

**具有继承性的多态:**
在 Python 中，多态允许我们在子类中定义与父类中的方法同名的方法。在继承中，子类从父类继承方法。但是，可以修改子类中从父类继承的方法。这在从父类继承的方法不太适合子类的情况下特别有用。在这种情况下，我们在子类中重新实现该方法。这个在子类中重新实现方法的过程被称为**方法覆盖**。

## 蟒蛇 3

```
class Bird:
  def intro(self):
    print("There are many types of birds.")

  def flight(self):
    print("Most of the birds can fly but some cannot.")

class sparrow(Bird):
  def flight(self):
    print("Sparrows can fly.")

class ostrich(Bird):
  def flight(self):
    print("Ostriches cannot fly.")

obj_bird = Bird()
obj_spr = sparrow()
obj_ost = ostrich()

obj_bird.intro()
obj_bird.flight()

obj_spr.intro()
obj_spr.flight()

obj_ost.intro()
obj_ost.flight()
```

**Output:** 

```
There are many types of birds.
Most of the birds can fly but some cannot.
There are many types of birds.
Sparrows can fly.
There are many types of birds.
Ostriches cannot fly.
```

**带有函数和对象的多态性:**
也可以创建一个可以接受任何对象的函数，允许多态性。在这个例子中，让我们创建一个名为“func()”的函数，它将接受一个我们将命名为“obj”的对象。虽然我们使用的名称是“obj”，但是任何实例化的对象都可以被调用到这个函数中。接下来，让我们使用传递给它的‘obj’对象给函数做一些事情。在这种情况下，让我们调用三个方法，即。，大写()，语言()和类型()，每个都在“印度”和“美国”两个类别中定义。接下来，让我们创建“印度”和“美国”类的实例，如果我们还没有它们的话。有了这些，我们可以使用相同的 func()函数调用它们的动作:

## 蟒蛇 3

```
def func(obj):
    obj.capital()
    obj.language()
    obj.type()

obj_ind = India()
obj_usa = USA()

func(obj_ind)
func(obj_usa)
```

**代码:**用函数
实现多态性

## 蟒蛇 3

```
class India():
    def capital(self):
        print("New Delhi is the capital of India.")

    def language(self):
        print("Hindi is the most widely spoken language of India.")

    def type(self):
        print("India is a developing country.")

class USA():
    def capital(self):
        print("Washington, D.C. is the capital of USA.")

    def language(self):
        print("English is the primary language of USA.")

    def type(self):
        print("USA is a developed country.")

def func(obj):
    obj.capital()
    obj.language()
    obj.type()

obj_ind = India()
obj_usa = USA()

func(obj_ind)
func(obj_usa)
```

**Output:** 

```
New Delhi is the capital of India.
Hindi is the most widely spoken language of India.
India is a developing country.
Washington, D.C. is the capital of USA.
English is the primary language of USA.
USA is a developed country.
```