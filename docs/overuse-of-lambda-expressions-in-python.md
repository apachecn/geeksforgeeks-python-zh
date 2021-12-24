# Python 中 lambda 表达式的过度使用

> 原文:[https://www . geesforgeks . org/overuse-of-lambda-expressions-in-python/](https://www.geeksforgeeks.org/overuse-of-lambda-expressions-in-python/)

**什么是λ表达式？**
lambda 表达式是一种特殊的语法，用于创建没有名称的函数。这些函数被称为[λ函数](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)。这些 lambda 函数可以有任意数量的参数，但只能有一个表达式和一个隐式返回语句。Lambda 表达式返回函数对象。例如，考虑λ表达式:

```
lambda (arguments) : (expression)
```

这个 lambda 表达式定义了一个**未命名函数**，它接受两个参数并返回两个参数的和。但是我们如何调用一个未命名的函数呢？上面定义的未命名的**λ函数**可以称为:

```
(lambda x, y: x + y)(1, 2)
```

**代码 1:**

## 蟒蛇 3

```
# Python program showing a use
# lambda function

# performing a addition of three number
x1 = (lambda x, y, z: (x + y) * z)(1, 2, 3)
print(x1)

# function using a lambda function     
x2 = (lambda x, y, z: (x + y) if (z == 0) else (x * y))(1, 2, 3)
print(x2)      
```

**输出:**

```
9
2
```

虽然不鼓励这样做，但是 lambda 表达式返回的函数对象可以赋给一个变量。参见下面的例子，其中变量 sum 被赋值给 lambda 表达式返回的函数对象。

## 蟒蛇 3

```
# Python program showing
# variable is storing lambda
# expression

# assingned to a variable
sum = lambda x, y: x + y
print(type(sum))

x1 = sum(4, 7)
print(x1)
```

**输出:**

```
11
```

**λ表达式的常用用法:**

*   由于 lambda 函数是匿名的，不需要指定名称，所以它们通常被**用来调用需要函数对象作为参数的函数(或类)**。为这样的函数参数定义单独的函数是没有用的，因为函数定义通常很短，在代码中只需要一两次。例如，内置函数的**键**参数，[排序为()](https://www.geeksforgeeks.org/sorted-function-python/)。

## 蟒蛇 3

```
# Python program showing
# using of normal function
def Key(x):
    return x%2
nums = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
sort = sorted(nums, key = Key)
print(sort)
```

*   **输出:**

```
[0, 2, 4, 6, 8, 1, 3, 5, 7, 9]
```

## 蟒蛇 3

```
# Python program showing use
# of lambda function

nums = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
sort_lambda = sorted(nums, key = lambda x: x%2)
print(sort_lambda)
```

*   **输出:**

```
[0, 2, 4, 6, 8, 1, 3, 5, 7, 9]
```

*   Lambda 函数是[内联函数](https://www.geeksforgeeks.org/inline-functions-cpp/)，因此只要需要重复函数调用来减少执行时间，它们就是**。此类场景的一些示例是函数: [map()](https://www.google.com/amp/s/www.geeksforgeeks.org/python-map-function/amp/) 、 [filter()](https://www.google.com/amp/s/www.geeksforgeeks.org/filter-in-python/amp/) 和 sorted()。例如** 

## 蟒蛇 3

```
# Python program showing a use
# of lambda function

nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

# using map() function
squares = map(lambda x: x * x, nums)
print(list(squares))

# using filter() function
evens = filter(lambda x: True if (x % 2 == 0)
                              else False, nums)
print(list(evens))
```

**λ函数的利弊:**
**λ函数的利弊:**

*   由于是匿名的，lambda 函数可以很容易地传递，而无需分配给变量。
*   Lambda 函数是内联函数，因此执行速度相对较快。
*   很多时候，lambda 函数通过避免函数调用导致的逻辑跳转，使得代码可读性更好。例如，阅读以下代码块。

## 蟒蛇 3

```
# Python program performing
# operation using def()
def fun(x, y, z):
    return x*y+z
a = 1
b = 2
c = 3

# logical jump
d = fun(a, b, c)
print(d)    
```

*   **输出:**

```
5
```

## 蟒蛇 3

```
# Python program performing
# operation using lambda

d = (lambda x, y, z: x*y+z)(1, 2, 3)
print(d)
```

*   **输出:**

```
5
```

**λ函数的缺点:**

*   Lambda 函数只能有一个表达式。
*   Lambda 函数不能有 docstring。
*   很多时候 lambda 函数使得代码难以阅读。例如，参见下面给出的代码块。

## 蟒蛇 3

```
def func(x):
    if x == 1:
        return "one"
    elif x == 2:
        return "two"
    elif x == 3:
        return "three"
    else:
        return "ten"
num = func(3)
print(num)
```

*   **输出:**

```
three
```

## 蟒蛇 3

```
# Python program showing use
# of lambda function
num = (lambda x: "one" if x == 1 else( "two" if x == 2
                       else ("three" if x == 3 else "ten")))(3)
print(num)
```

*   **输出:**

```
three
```

**λ表达式的误用:**

*   **lambda 表达式的赋值:**官方 python 风格指南 [PEP8](https://www.python.org/dev/peps/pep-0008/) 强烈反对赋值 lambda 表达式，如下例所示。

```
func = lambda x, y, z: x*y + z
```

*   相反，建议编写一个单行函数，

```
def func(x, y, z): return x*y + z 
```

*   虽然第二种方法鼓励 lambda 函数是匿名的，但它对于调试期间的回溯也很有用。运行下面的代码，看看**如何定义**让回溯变得更有用。

## 蟒蛇 3

```
func = lambda x, y, z: x * y + z
print(func)
def func(x, y, z): return x * y + z
print(func)
```

*   **围绕函数包装 lambda 表达式:**很多时候，lambda 表达式是不必要的围绕函数包装的，如下图所示。

```
nums = [-2, -1, 0, 1, 2]
sort = sorted(nums, key=lambda x: abs(x))
```

*   虽然上面的语法绝对正确，但是程序员必须明白 python 中的所有函数都可以作为函数对象传递。因此，相同的代码可以(也应该)写成，

```
sort = sorted(nums, key=abs)
```

*   **不必要地传递函数:**很多时候，程序员传递的函数只执行一个操作。请参见以下代码。

```
nums = [1, 2, 3, 4, 5]
summation = reduce(lambda x, y: x + y, nums)
```

*   上面传递的 lambda 函数只执行一个操作，将两个参数相加。使用内置函数**和**可以得到同样的结果，如下图所示。

```
nums = [1, 2, 3, 4, 5]
summation = sum(nums)
```

*   程序员应该避免在常见操作中使用 lambda 表达式，因为很有可能内置函数会提供相同的结果。

**过度使用λ表达式:**

*   **对非平凡函数使用 lambda:**有时候，简单函数也可以是非平凡的。请参见下面的代码。

## 蟒蛇 3

```
details = [{'p':100, 'r':0.01, 'n':2, 't':4},
           {'p':150, 'r':0.04, 'n':1, 't':5},
           {'p':120, 'r':0.05, 'n':5, 't':2}]
sorted_details = sorted(details,
                        key=lambda x: x['p']*((1 + x['r']/
                                x['n'])**(x['n']*x['t'])))
print(sorted_details)
```

*   **输出:**

> [{'n': 2，' r': 0.01，' t': 4，' p': 100}，{'n': 5，' r': 0.05，' t': 2，' p': 120}，{'n': 1，' r': 0.04，' t': 5，' p': 150}]

*   在这里，我们以[复利](https://www.geeksforgeeks.org/compound-interest/)为基础对字典进行整理。现在，看下面写的代码，它使用 **def** 。

## 蟒蛇 3

```
details = [{'p':100, 'r':0.01, 'n':2, 't':4},
           {'p':150, 'r':0.04, 'n':1, 't':5},
           {'p':120, 'r':0.05, 'n':5, 't':2}]
def CI(det):
    '''sort key: coumpound interest, P(1 + r/n)^(nt)'''
    return det['p']*((1 + det['r']/det['n'])**(det['n']*det['t']))
sorted_details = sorted(details, key=CI)
print(sorted_details)
```

*   **输出:**

> [{'n': 2，' r': 0.01，' t': 4，' p': 100}，{'n': 5，' r': 0.05，' t': 2，' p': 120}，{'n': 1，' r': 0.04，' t': 5，' p': 150}]

*   虽然两个代码都做了同样的事情，但是第二个使用 **def** 的代码可读性更好。这里写在 lambda 下的表达式可能很简单，但它有一个含义(复利公式)。因此，这个表达不是无足轻重的，值得一个名字。对非平凡函数使用 lambda 表达式会降低代码的可读性。
*   **多行时使用 lambdas 会有帮助:**如果使用多行函数使代码更易读，那么使用 lambda 表达式减少一些代码行是不值得的。例如，请参见下面的代码。

> people = [('sam '，' M '，18)、(' susan '，' F '，22)、(' joy '，' M '，21)、(' lucy '，' F '，12)]
> sorted _ people = sorted(people，key=lambda x: x[1])

*   另请参见下面使用 **def** 的代码。

```
def Key(person):
    name, sex, age = person
    return sex
sorted_people = sorted(people, key=Key)
```

*   看看第二个代码块中的元组解包是如何使它更具可读性和逻辑性的。代码的可读性应该是在协作环境中工作的程序员的首要任务。
*   **使用 lambda 表达式进行 map 和 filter:**lambda 非常常用于 map()和 filter()，如图所示。

## 蟒蛇 3

```
nums = [0, 1, 2, 3, 4, 5]
mapped = map(lambda x: x * x, nums)
filtered = filter(lambda x: x % 2, nums)
print(list(mapped))
print(list(filtered))
```

*   下面是另一个代码块，它使用[生成器表达式](https://www.geeksforgeeks.org/generator-expressions/)来获得类似的结果。

## 蟒蛇 3

```
nums = [0, 1, 2, 3, 4, 5]
mapped = (x * x for x in nums)
filtered = (x for x in nums if x % 2 == 1)
print(list(mapped))
print(list(filtered))
```

*   与 map()和 filter()不同，生成器表达式是 python 语言的通用特性。因此，生成器增强了代码的可读性。而 map()和 filter()需要这些函数的先验知识。

*   **高阶函数的使用:**接受其他函数对象作为自变量的函数称为[高阶函数](https://www.geeksforgeeks.org/higher-order-functions-currying/)(即 map()和 filter())，在[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)中很常见。如上所述，lambda 表达式通常用作高阶函数的函数参数。比较下面显示的两个代码块。
    使用高阶函数减少()

```
nums = [1, 2, 3, 4, 5]
product = reduce(lambda x, y: x*y, nums, 1)
```

*   不使用高阶函数

```
nums = [1, 2, 3, 4, 5]
def multiply(nums):
    prod = 1
    for number in nums:
        prod *= number
    return prod
product = multiply(nums)
```

*   虽然第一个代码块使用的代码行更少，也不难理解，但没有函数式编程背景的程序员会发现第二个代码块可读性更好。除非实践正确的函数式编程范式，否则将一个函数传递给另一个函数是不受欢迎的，因为这会降低可读性。