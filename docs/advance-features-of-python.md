# Python 的高级特性

> 原文:[https://www.geeksforgeeks.org/advance-features-of-python/](https://www.geeksforgeeks.org/advance-features-of-python/)

Python 是一种高级解释编程语言，语法简单。 [Python](https://www.geeksforgeeks.org/python-programming-language/) 代码是逐行编译的，这使得错误的调试变得更加容易和高效。Python 几乎适用于所有类型的平台，如 Windows、Mac、Linux、树莓 Pi 等。Python 支持模块和包，这鼓励程序模块化和代码重用。Python 可用于处理大量数据和执行复杂的数学问题，也可用于应用程序的开发。

## Python 的高级特性

#### 发电机

[生成器](https://www.geeksforgeeks.org/generators-in-python/)函数允许我们声明一个行为与迭代器相同的函数，即它可以用来代替 for 循环。生成器是迭代器，但是它们只能迭代一次。生成器引入了 Python 中的 [yield](https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/) 语句，这个语句有点像 return，因为它返回值。生成器将创建元素，并仅在需要时将它们存储在内存中，即一次一个。这意味着，如果你必须创建大量的浮点数，你只能一次一个地将它们存储在内存中！。这大大简化了代码，使代码比简单的 for 循环更有效。
**例 1:-**

```py
# A simple generator function
def my_func():
    n = 1
    print('First Number')
    # Generator function contains yield statements
    yield n

    n += 1
    print('Second Number ')
    yield n

    n += 1
    print('Last Number ')
    yield n

# Using for loop
for number in my_func():
    print(number)    
```

**输出:**

```py
First Number
1
Second Number 
2
Last Number 
3

```

 **例 2:-** 

```py
def str(my_str):
    length = len(my_str)
    for i in range(0, length ):
        yield my_str[i]

# For loop to print the string as 
# it is using generators and for loop.
for char in str("Shivam And Sachin"):
    print(char, end ="")
```

**输出:**

```py
Shivam And Sachin

```

**注意:**更多信息请参考 Python 中的[生成器](https://www.geeksforgeeks.org/generators-in-python/)

#### 装饰者

[装饰者](https://www.geeksforgeeks.org/decorators-in-python/)是 Python 的重要组成部分。它们非常有助于为之前实现的函数添加功能，而不会对原始函数进行任何更改。在 Decorators 中，函数作为参数传递给另一个函数，然后在包装函数中调用。它们允许我们包装另一个函数，以便扩展包装函数的功能，而无需永久修改它。装饰器通常在定义你想要装饰的函数之前被调用。当你想给现有代码一个更新的代码时，装饰器是非常有效的。

 **例 1:-** 

```py
def decorator(a_func):

    def wrapper():
        print("Before executing function requiring decoration.")

        a_func()

        print("After executing requiring decoration.")

    return wrapper

def function():
    print("Function requiring decoration.")

function()

function = decorator(function)

function()
```

**输出:**

```py
Function requiring decoration.
Before executing function requiring decoration.
Function requiring decoration.
After executing requiring decoration.

```

 **例 2:-** 

```py
def flowerDecorator(func):
    def newFlowerPot(n):
        print("We are decorating the flower vase.")
        print("You wanted to keep % d flowers in the vase." % n)

        func(n)

        print("Our decoration is done.")

    return newFlowerPot

def flowerPot(n):
    print("We have a flower vase.")

flowerPot = flowerDecorator(flowerPot)
flowerPot(5)
```

**输出:**

```py
We are decorating the flower vase.
You wanted to keep 5 flowers in the vase.
We have a flower vase.
Our decoration is done.

```

**注意:**更多信息请参考 Python 中的[装饰者](https://www.geeksforgeeks.org/decorators-in-python/)

#### λ函数

[Lambda](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/) 函数是一个小型匿名函数。这些类型的函数可以接受任意数量的参数，但只能有一个表达式。普通函数使用`def`关键字定义，而匿名函数使用关键字“`lambda`”定义。Lambda 函数不需要 return 语句，它们总是返回通过评估 lambda 表达式获得的值。

**示例:-3 个数字相乘的代码。**

```py
x = lambda a, b, c : a * b*c
print(x(5, 4, 3))
```

**输出:**

```py
60

```

**例:-加 3 个数的代码。**

```py
x = lambda a, b, c : a + b+c
print(x(12, 40, 8))
```

**输出:**

```py
60

```

**注:**更多信息请参考 [Python lambda](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

#### 地图

`Map()`是一个内置的 Python 函数，用于将函数应用于一系列元素，如列表或字典，并返回结果列表。Python map 对象是一个迭代器，所以我们可以迭代它的元素。我们还可以将地图对象转换为序列对象，如列表、元组等。这是一种简单有效的操作方式，例如映射两个列表或对列表或字典的元素进行排序。

 **示例:-将字符串转换为其长度的代码。
T3】**

```py
def func(n):
    return len(n)

a =('Singla', 'Shivam', 'Sachin')
x = map(func, a)
print(a)

# convert the map into a list,
#  for readability:
print(list(x))
```

**输出:**

```py
('Singla', 'Shivam', 'Sachin')
[6, 6, 6]

```

 **示例:-将数字映射到其立方体的代码。
T3】**

```py
numbers = (1, 2, 3, 4)
res = map(lambda x: x * x*x, numbers)

# converting map object to list
numbersCube = list(res)
print(numbersCube)
```

**输出:**

```py
[1, 8, 27, 64]

```

**注意:**更多信息请参考 [Python 地图()函数](https://www.geeksforgeeks.org/python-map-function/)

#### 过滤器

`Filter()` 是一个内置函数，与 Map 函数非常相似，因为它将函数应用于序列(元组、字典、列表)。主要区别在于 filter()函数将一个函数和一个序列作为参数，并返回一个 iterable，只产生函数返回 True 的序列中的项目，而序列中计算结果为 False 的所有项目都被移除。简单地说，filter()方法从函数返回 true 的可迭代表的元素中构造一个迭代器。

 **例 1:-** 

```py
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10,
          11, 12, 13, 14, 15, 16, 17, 18, 19, 20]

# Function that filters out all 
# numbers which are multiple of 4
def filter_numbers(num):

    if num % 4 == 0:
        return True
    else:
        return False

filtered_numbers = filter(filter_numbers, numbers)
filters = list(filtered_numbers)
print(filters)
```

**输出:**

```py
[4, 8, 12, 16, 20]

```

 **例 2:-** 

```py
# To sort all ages which 
# are above 20 years
ages = [35, 21, 17, 18, 24,
        32, 50, 59, 26, 6, 14]

def Func(x):
  if x < 20:
    return False
  else:
    return True

adults = filter(Func, ages)

for z in adults:
  print(z)
```

**输出:**

```py
35
21
24
32
50
59
26

```

**注意:**更多信息请参考 python 中的[过滤器()](https://www.geeksforgeeks.org/filter-in-python/)

#### 拉链和拉开拉链

`Zip()`是一个内置的 Python 函数，它为我们提供了元组的迭代器。Zip 是一种保存真实数据的容器。它将可迭代元素作为输入，并返回它们的迭代器(元组的迭代器)。它从左到右计算可迭代的。我们可以使用结果迭代器快速有效地解决常见的编程问题，比如创建字典。解压只是解压的相反过程，解压时我们使用带有`zip()`功能的*字符。

**实施例 1:-**

```py
# ZIPPING 
a = ("SHIVAM", "SACHIN", "VIKALP", "RAGHAV", "PRANAY")
b = ("SINGLA", "SINGLA", "GARG", "GUPTA", "GUPTA")

x = zip(a, b)

# use the tuple() function to display
#  a readable version of the result:
print(tuple(x))
```

**输出:**

> ((“SHIVAM”、“SINGLA”)、(“SACHIN”、“SINGLA”)、(“VIKALP”、“GARG”)、(“RAGHAV”、“GUPTA”)、(“PRANAY”、“GUPTA”))

**实施例 2:-**

```py
# ZIPPING AND UNZIPPING
name = ['sachin', 'shivam', 'vikalp']
age = [20, 18, 19]

result = zip(name, age)
result_list = list(result)
print(result_list)

n, a = zip(*result_list)

print('name =', n)
print('age =', a)
```

**输出:**

```py
[('sachin', 20), ('shivam', 18), ('vikalp', 19)]
name = ('sachin', 'shivam', 'vikalp')
age = (20, 18, 19)

```