# Python 中方法重载和方法覆盖的区别

> 原文:[https://www . geesforgeks . org/python 中方法重载和方法重写的区别/](https://www.geeksforgeeks.org/difference-between-method-overloading-and-method-overriding-in-python/)

[**方法重载:**](https://www.geeksforgeeks.org/python-method-overloading/)
方法重载是编译时多态性的一个例子。在这种情况下，同一类的多个方法共享具有不同签名的相同方法名。方法重载用于向方法的行为中添加更多内容，并且方法重载不需要多个类。
**注意:** Python 不支持方法重载。我们可能会重载方法，但只能使用最新定义的方法。
**例:**

## 蟒蛇 3

```py
# Function to take multiple arguments
def add(datatype, *args):

    # if datatype is int
    # initialize answer as 0
    if datatype =='int':
        answer = 0

    # if datatype is str
    # initialize answer as ''
    if datatype =='str':
        answer =''

    # Traverse through the arguments
    for x in args:

        # This will do addition if the 
        # arguments are int. Or concatenation 
        # if the arguments are str
        answer = answer + x

    print(answer)

# Integer
add('int', 5, 6)

# String
add('str', 'Hi ', 'Geeks')
```

**输出:**

```py
11
Hi Geeks
```

[**方法覆盖:**](https://www.geeksforgeeks.org/method-overriding-in-python/)
方法覆盖是运行时多态性的一个例子。在这种情况下，父类已经提供的方法的具体实现由子类提供。它用于更改现有方法的行为，并且至少需要两个类来重写方法。在方法重写中，继承总是必需的，因为它是在父类(超类)和子类(子类)方法之间完成的。
**python 中方法覆盖的例子:**

## 蟒蛇 3

```py
class A:

    def fun1(self):
        print('feature_1 of class A')

    def fun2(self):
        print('feature_2 of class A')

class B(A):

    # Modified function that is
    # already exist in class A
    def fun1(self):
        print('Modified feature_1 of class A by class B')   

    def fun3(self):
        print('feature_3 of class B')

# Create instance
obj = B()

# Call the override function
obj.fun1()
```

**输出:**

```py
Modified feature_1 of class A by class B
```

**Python 中方法重载和方法覆盖的区别:**

<figure class="table">

| S.NO | 方法重载 | 方法重写 |
| --- | --- | --- |
| 1. | 在方法重载中，方法或函数必须具有相同的名称和不同的签名。 | 而在方法重写中，方法或函数必须具有相同的名称和签名。 |
| 2. | 方法重载是编译时多态性的一个例子。 | 而方法重写是运行时多态性的一个例子。 |
| 3. | 在方法重载中，可能需要也可能不需要继承。 | 而在方法重写中，总是需要继承。 |
| 4. | 方法重载在类内的方法之间执行。 | 而方法重写是在父类和子类方法之间完成的。 |
| 5. | 使用它是为了给方法的行为增加更多的东西。 | 而它是用来改变现有方法的行为的。 |
| 6. | 在方法重载中，不需要一个以上的类。 | 而在方法重写中，至少需要两个类。 |

</figure>