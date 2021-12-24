# Python 中“_ _ eq _ _”VS”的区别是“VS”= = =“

> 原文:[https://www . geesforgeks . org/difference-in-eq _ _-vs-is-vs-in-python/](https://www.geeksforgeeks.org/difference-between-__eq__-vs-is-vs-in-python/)

有多种方法可以用来比较 Python 中任何类型的对象。Python 有“ **==** ”运算符，“**是**”运算符，还有“**_ _ eq _ _**”dunder 方法用于比较一个类的两个对象或自定义比较。本文解释了上述三种操作符以及它们之间的区别。

## ==运算符

“==”运算符比较两个对象的值或相等性，而 Python“is”运算符检查两个变量是否指向内存中的同一个对象。

**例 1:**

## 蟒蛇 3

```py
# lists initialization
x = [1, 2]
y = [1, 2]

z = y

# comparisons
print("x == y : ", x == y)
print("z == y : ", z == y)

# location in memory
print("Location of x is ", id(x))
print("Location of y is ", id(y))
print("Location of z is ", id(z))
```

**Output**

```py
x == y :  True
z == y :  True
Location of x is  140169895643144
Location of y is  140169895642952
Location of z is  140169895642952

```

**例 2:**

## 蟒 3

```py
class Student:
    def __init__(self, name):
        self.name = name

divyansh = Student("Divyansh")
shivansh = Student("Divyansh")

print("divyansh == shivansh : ", (divyansh == shivansh))
```

**输出**

```py
divyansh == shivansh :  False

```

在上面的例子中，我们应该得到一个输出 **True** ，但是我们得到的输出却是 **False** 。这是因为，对于用户定义类的对象，我们需要指定如何比较它们。我们创建的**学生**对象不知道两个学生平等的标准是什么，也许他们有相同的属性“名字”，也许他们有一堆其他的特征。我们要说一个学生对象与另一个学生对象相同，需要相同的是什么。嗯，这就是我们要通过在那里实现一个名为 **__eq__** 的方法来指定的。这是 Python 中的 [**dunder 方法之一**](https://www.geeksforgeeks.org/dunder-magic-methods-python/) 。它允许我们覆盖 Python 中“ **==** ”运算符的基本功能。

**例 3:**

## 蟒 3

```py
class Student:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        if isinstance(other, Student):
            if other.name == self.name:
                return True
        return False

divyansh = Student("Divyansh")
shivansh = Student("Divyansh")

print("divyansh == shivansh : ", (divyansh == shivansh))
```

**输出**

```py
divyansh == shivansh :  True

```

实现这个 dunder 方法，“ **==** ”运算符在 Student 类的两个对象之间使用，得到一个精确的值比较，现在如果我把这个切换到“**是**运算符，这个就不一样了。

**例 4:**

## 蟒蛇 3

```py
class Student:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        if isinstance(other, Student):
            if other.name == self.name:
                return True
        return False

divyansh = Student("Divyansh")
shivansh = Student("Divyansh")

print("divyansh is shivansh : ", (divyansh is shivansh))
```

**Output**

```py
divyansh is shivansh :  False

```

在上面的代码片段中，我们收到了 **False** 作为输出，这是因为**div Yans**将与 **shivansh** 不同，尽管这些对象具有相同的值。然而，它们具有不同的存储位置，即它们是不同的和唯一的对象，可以在任何时间点独立地改变它们的属性。

**例 5:**

## 蟒 3

```py
class Student:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        if isinstance(other, Student):
            if other.name == self.name:
                return True
        return False

divyansh = Student("Divyansh")
shivansh = divyansh

print("divyansh is shivansh : ", (divyansh is shivansh))
```

**输出**

```py
divyansh is shivansh :  True

```

在上面的例子中，输出是**真，**这是因为 shivansh 指向 divyansh 指向的同一个 Student 对象。

## “is”运算符

“is”运算符比较两个对象的标识。这里我们比较对象本身。

**例 6:**

## 蟒 3

```py
x = [1, 2]
y = [1, 2]
z = y
print("x is y : ", x is y)
print("z is y : ", z is y)
print("Location of x is ", id(x))
print("Location of y is ", id(y))
print("Location of z is ", id(z))
```

**输出**

```py
x is y :  False
z is y :  True
Location of x is  139987316430856
Location of y is  139987316430664
Location of z is  139987316430664

```

在上例中，即使 x 和 y 具有相同的值，它们也会将它们存储在内存中的不同位置。所以很明显，即使对象在值方面是相同的，它们在内存中的位置实际上是不同的。我们还看到在上面的片段**中 z 是 y** 给出 **True** ，这是因为这些物体实际上是相同的，即 y 的位置和上面 z 的位置完全相同。