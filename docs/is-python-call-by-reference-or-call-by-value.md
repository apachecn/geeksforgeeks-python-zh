# Python 是引用调用还是值调用

> 原文:[https://www . geesforgeks . org/is-python-按引用调用或按值调用/](https://www.geeksforgeeks.org/is-python-call-by-reference-or-call-by-value/)

Python 利用了一种系统，这种系统被称为“按对象引用调用”或“按赋值调用”。如果将整数、字符串或元组之类的参数传递给函数，这种传递就像按值调用，因为您不能更改传递给函数的不可变对象的值。而传递可变对象可以被认为是通过引用的调用，因为当它们的值在函数内部改变时，它也会反映在函数外部。
**例 1:**

## 蟒蛇 3

```py
# Python code to demonstrate
# call by value

string = "Geeks"

def test(string):

    string = "GeeksforGeeks"
    print("Inside Function:", string)

# Driver's code
test(string)
print("Outside Function:", string)
```

**输出**T2】

```py
Inside Function: GeeksforGeeks
Outside Function: Geeks
```

**例 2**

## 蟒蛇 3

```py
# Python code to demonstrate
# call by reference

def add_more(list):
    list.append(50)
    print("Inside Function", list)

# Driver's code
mylist = [10,20,30,40]

add_more(mylist)
print("Outside Function:", mylist)
```

**输出**T2】

```py
Inside Function [10, 20, 30, 40, 50]
Outside Function: [10, 20, 30, 40, 50]
```

#### 将名称绑定到对象

在 python 中，我们赋予值/容器的每个变量都被视为一个对象。当我们给一个变量赋值时，我们实际上是把一个名字绑定到一个 T2 对象上。

## 蟒蛇 3

```py
a = "first"
b = "first"

# Returns the actual location
# where the variable is stored
print(id(a))

# Returns the actual location
# where the variable is stored
print(id(b))

# Returns true if both the variables
# are stored in same location
print(a is b)
```

**输出**T2】

```py
110001234557894
110001234557894
True
```

现在，让我们试着用另一个例子来更好地理解这一点。
**例 2:**

## 蟒蛇 3

```py
a = [10, 20, 30]
b = [10, 20, 30]

# return the location
# where the variable
# is stored
print(id(a))

# return the location
# where the variable
# is stored
print(id(b))

# returns false if the
# location is not same
print(a is b)
```

**输出**T2】

```py
541190289536222
541190288737777
False
```

上面两个例子的输出不同，因为列表是**可变的**，字符串是**不可变的**。一个**不可变的**变量一旦创建就不能改变。如果我们希望改变一个**不可变的**变量，比如一个字符串，我们必须创建一个新的实例，并将该变量绑定到新的实例。反之，**可变**变量可以就地改变。
**例 3:**

## 蟒蛇 3

```py
def foo(a):

    # A new variable is assigned
    # for the new string
    a = "new value"
    print("Inside Function:", a)

# Driver's code
string = "old value"
foo(string)

print("Outside Function:", string)
```

**输出:**

```py
Inside Function: new value
Outside Function: old value
```

在上面的例子中，一个属于**不可变**类型对象的字符串作为参数被传递给函数 foo。在给定函数 foo 的范围内，a= "new value "被绑定到与 string 被绑定到外部的对象相同的对象。在函数 foo 的范围内，我们将“旧值”修改为“新值”。一旦我们离开 function foo 的范围，名称空间中就不再有 a =“new value”，而 string 所引用的值也从未更改过。
**示例 4:** 现在，让我们看看**可变变量**是如何传递到函数中的。

## 蟒蛇 3

```py
def foo(a):
    a[0] = "Nothing"

# Driver' code
bar = ['Hi', 'how', 'are', 'you', 'doing']
foo(bar)
print(bar)
```

**输出:**

```py
['Nothing, 'how', 'are', 'you', 'doing']
```

当我们将一个可变变量传递到 function foo 中，并将其修改为其他名称时，function foo 仍然指向该对象，并在其执行过程中继续指向该对象。