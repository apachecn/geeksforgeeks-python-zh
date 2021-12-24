# python 中的 bool()

> 原文:[https://www.geeksforgeeks.org/bool-in-python/](https://www.geeksforgeeks.org/bool-in-python/)

**Python bool()函数**用于使用标准的真值测试程序，将一个值返回或转换为布尔值，即 True 或 False。

> **语法:** bool([x])

### bool()参数

bool()方法通常只接受一个参数(这里是 x)，在这个参数上可以应用标准的真值测试过程。**如果没有参数通过，那么默认返回假**。因此，传递参数是可选的。

### 从 bool()返回值

它可以返回两个值中的一个。

*   如果传递的参数或值为真，则返回真。
*   如果传递的参数或值为假，则返回假。

这里有几个例子，Python 的 bool()方法返回 false。除了这些，所有其他值都返回真。

*   如果传递了假值。
*   如果没有通过。
*   如果传递了空序列，如()、[]、"，等等
*   如果零以任何数字类型传递，如 0、0.0 等
*   如果传递了空映射，如{}。
*   如果类的对象具有 __bool__()或 __len()__ 方法，则返回 0 或 False

## bool()函数 Python 示例:

**例 1:**

## 蟒蛇 3

```py
# Python program to illustrate
# built-in method bool()

# Returns False as x is False
x = False
print(bool(x))

# Returns True as x is True
x = True
print(bool(x))

# Returns False as x is not equal to y
x = 5
y = 10
print(bool(x == y))

# Returns False as x is None
x = None
print(bool(x))

# Returns False as x is an empty sequence
x = ()
print(bool(x))

# Returns False as x is an empty mapping
x = {}
print(bool(x))

# Returns False as x is 0
x = 0.0
print(bool(x))

# Returns True as x is a non empty string
x = 'GeeksforGeeks'
print(bool(x))
```

**输出:**

```py
False
True
False
False
False
False
False
True
```

**例 2:**

这里有一个利用 bool()方法找出偶数和奇数的程序。您可以使用其他输入并检查结果。

## 蟒蛇 3

```py
# Python code to check whether a number
# is even or odd using bool()

def check(num):
    return(bool(num % 2 == 0))

# Driver Code
num = 8
if(check(num)):
    print("Even")
else:
    print("Odd")
```

**输出:**

```py
Even
```

## Python 输入中的 bool()

这里我们用 bool()函数接受布尔类型的布尔值(真/假)输入，并检查它是返回真还是假。

## 蟒蛇 3

```py
user_input = bool(input("Are you hungry? True or false: "))
if user_input == "True":
    print(" You need to eat some foods ")
else:
    print("Let's go for walk")
```

**输出:**

```py
Are you hungry? True or false: False
Let's go for walk
```