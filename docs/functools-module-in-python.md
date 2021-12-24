# Python 中的功能工具模块

> 原文:[https://www.geeksforgeeks.org/functools-module-in-python/](https://www.geeksforgeeks.org/functools-module-in-python/)

**功能工具**模块用于处理其他功能的高阶功能。它提供了用于处理其他函数的函数和可调用对象，以便在不完全重写它们的情况下使用或扩展它们。本模块有两个类–**部分**和**部分**。

## 部分类别

部分函数是特定参数值的原始函数。它们可以通过使用 functools 库中的“部分”在 Python 中创建。`__name__`和`__doc__`属性由程序员创建，因为它们不是自动创建的。`partial()`创建的对象有三个只读属性:

**语法:**

```py
partial(func[, *args][, **keywords])
```

*   **partial . func**–返回父函数的名称和十六进制地址。
*   **partial . args**–返回 partial 函数中提供的位置参数。
*   **partial . keywords**–返回 partial 函数中提供的关键字参数。

**示例:**

```py
from functools import partial

def power(a, b):
    return a**b

# partial functions
pow2 = partial(power, b = 2)
pow4 = partial(power, b = 4)
power_of_5 = partial(power, 5)

print(power(2, 3))
print(pow2(4))
print(pow4(3))
print(power_of_5(2))

print('Function used in partial function pow2 :', pow2.func)
print('Default keywords for pow2 :', pow2.keywords)
print('Default arguments for power_of_5 :', power_of_5.args)
```

**输出:**

> 8
> 16
> 81
> 25
> 在部分功能 pow2 中使用的功能:<功能 pow 在 0x 000001 cbbe 8 c7b 8>T4【pow 2 的默认关键字:{ ' b ':2 }
> pow _ of _ 5 的默认参数:(5，)

## Partialmethod 类

它是已经为特定参数定义的函数的方法定义，如分部函数。但是，它不可调用，只是一个方法描述符。它返回一个新的 partialmethod 描述符。

**语法:**

```py
partialmethod(func, *args, **keywords)
```

**示例:**

```py
from functools import partialmethod

class Demo:
    def __init__(self):
        self.color = 'black'
    def _color(self, type):
        self.color = type

    set_red = partialmethod(_color, type ='red')
    set_blue = partialmethod(_color, type ='blue')
    set_green = partialmethod(_color, type ='green')

obj = Demo()
print(obj.color)
obj.set_blue()
print(obj.color)
```

**输出:**

```py
black
blue

```

## 功能

*   **Cmp_to_key**

    它将比较函数转换为键函数。对于不同的条件，比较函数必须返回 1、-1 和 0。它可以用在诸如 sorted()、min()、max()等关键函数中。

    **语法:**

    ```py
    function(iterable, key=cmp_to_key(cmp_function)) 
    ```

    **示例:**

    ```py
    from functools import cmp_to_key

    # function to sort according to last character
    def cmp_fun(a, b):
        if a[-1] > b[-1]:
            return 1
        elif a[-1] < b[-1]:
            return -1
        else:
            return 0

    list1 = ['geeks', 'for', 'geeks']
    l = sorted(list1, key = cmp_to_key(cmp_fun))
    print('sorted list :', l)
    ```

    **输出:**

    ```py
    sorted list : ['for', 'geeks', 'geeks']

    ```

*   **Reduce**

    它对一个序列的元素重复应用两个参数的函数，以便将序列缩减为一个值。例如`reduce(lambda x, y: x^y, [1, 2, 3, 4])`计算`(((1^2)^3)^4)`。如果存在初始值，它将被放在计算的第一位，如果序列为空，则为默认结果。
    **语法:**

    ```py
    reduce(function, sequence[, initial]) -> value  
    ```

    **示例:**

    ```py
    from functools import reduce
    list1 = [2, 4, 7, 9, 1, 3]
    sum_of_list1 = reduce(lambda a, b:a + b, list1)

    list2 = ["abc", "xyz", "def"]
    max_of_list2 = reduce(lambda a, b:a if a>b else b, list2)

    print('Sum of list1 :', sum_of_list1)
    print('Maximum of list2 :', max_of_list2)
    ```

    **输出:**

    ```py
    Sum of list1 : 26
    Maximum of list2 : xyz

    ```

*   **Total_ordering**
    It is a class decorator that fills in the missing comparison methods `(__lt__, __gt__, __eq__, __le__, __ge__)`. If a class is given which defines one or more comparison methods, “@total_ordering” automatically supplies the rest as per the given definitions. However, the class must define one of `__lt__(), __le__(), __gt__(),` or `__ge__()` and additionally, the class should supply an `__eq__()` method.

    **示例:**

    ```py
    from functools import total_ordering

    @total_ordering
    class N:
        def __init__(self, value):
            self.value = value
        def __eq__(self, other):
            return self.value == other.value

        # Reverse the function of 
        # '<' operator and accordingly
        # other rich comparison operators
        # due to total_ordering decorator
        def __lt__(self, other):
            return self.value > other.value

    print('6 > 2 :', N(6)>N(2))
    print('3 < 1 :', N(3)<N(1))
    print('2 <= 7 :', N(2)<= N(7))
    print('9 >= 10 :', N(9)>= N(10))
    print('5 == 5 :', N(5)== N(5))
    ```

    **输出:**

    ```py
    6 > 2 : False
    3 < 1 : True
    2 = 10 : True
    5 == 5 : True

    ```

*   **Update_wrapper**

    它更新包装函数，使其看起来像包装函数。例如，在部分函数的情况下，我们可以通过使用 update_wrapper(partial，parent)来更新部分函数，使其看起来像它的父函数。这将把部分函数的文档(__doc__)和名称(__name__)更新为与父函数相同。

    **语法:**

    ```py
    update_wrapper(wrapper, wrapped[, assigned][, updated])
    ```

    **示例:**

    ```py
    from functools import update_wrapper, partial

    def power(a, b):
        ''' a to the power b'''
        return a**b

    # partial function
    pow2 = partial(power, b = 2)
    pow2.__doc__='''a to the power 2'''
    pow2.__name__ = 'pow2'

    print('Before wrapper update -')
    print('Documentation of pow2 :', pow2.__doc__)
    print('Name of pow2 :', pow2.__name__)
    print()
    update_wrapper(pow2, power)
    print('After wrapper update -')
    print('Documentation of pow2 :', pow2.__doc__)
    print('Name of pow2 :', pow2.__name__)
    ```

    **输出:**

    ```py
    Before wrapper update -
    Documentation of pow2 : a to the power 2
    Name of pow2 : pow2

    After wrapper update -
    Documentation of pow2 :  a to the power b
    Name of pow2 : power

    ```

*   **Wraps**
    It is a function decorator which applies update_wrapper() to the decorated function. It is equivalent to partial(update_wrapper, wrapped=wrapped, assigned=assigned, updated=updated).

    **示例:**

    ```py
    from functools import wraps

    def decorator(f):
        @wraps(f)
        def decorated(*args, **kwargs):
            """Decorator's docstring"""
            return f(*args, **kwargs)

        print('Documentation of decorated :', decorated.__doc__)
        return decorated

    @decorator
    def f(x):
        """f's Docstring"""
        return x

    print('f name :', f.__name__)
    print('Documentation of f :', f.__doc__)
    ```

    **输出:**

    ```py
    Documentation of decorated : f's Docstring
    f name : f
    Documentation of f : f's Docstring

    ```

*   **LRU_cache**

    LRU 缓存是一个函数装饰器，用于保存函数最近的最大调用。这可以在使用相同参数重复调用的情况下节省时间和内存。
    如果*maxsize*设置为 None，缓存可以无限制增长。如果* typed *为 True，不同数据类型的参数将被分别缓存。例如，f(1.0)和 f(1)将被清楚地记忆。

    **语法:**

    ```py
    lru_cache(maxsize=128, typed=False)
    ```

    **示例:**

    ```py
    from functools import lru_cache

    @lru_cache(maxsize = None)
    def factorial(n):
        if n<= 1:
            return 1
        return n * factorial(n-1)
    print([factorial(n) for n in range(7)])
    print(factorial.cache_info())
    ```

    **输出:**

    ```py
    [1, 1, 2, 6, 24, 120, 720]
    CacheInfo(hits=5, misses=7, maxsize=None, currsize=7)

    ```

*   **SingleDispatch**
    It is a function decorator. It transforms a function into a generic function so that it can have different behaviors depending upon the type of its first argument. It is used for function overloading, the overloaded implementations are registered using the register() attribute of the

    **示例:**

    ```py
    from functools import singledispatch

    @singledispatch
    def fun(s):
        print(s)
    @fun.register(int)
    def _(s):
        print(s * 2)

    fun('GeeksforGeeks')
    fun(10)
    ```

    **输出:**

    ```py
    GeeksforGeeks
    20

    ```