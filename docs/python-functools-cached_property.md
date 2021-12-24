# Python Functools–cached _ property()

> 原文:[https://www . geesforgeks . org/python-func tools-cached _ property/](https://www.geeksforgeeks.org/python-functools-cached_property/)

**@cached_property** 是一个装饰器，它将一个类的方法转换成一个属性，该属性的值只计算一次，然后作为一个普通属性进行缓存。因此，只要实例保持不变，缓存的结果就可用，我们可以将该方法用作类的属性，即

```py
Writing    : instance.method
Instead of : instance.method()

```

cached_property 是 Python 中 [functools 模块](https://www.geeksforgeeks.org/functools-module-in-python/)的一部分。它类似于`property()`，但是 cached_property()附带了一个额外的特性，那就是缓存。

**注意:**更多信息请参考 Python 中的[功能工具模块](https://www.geeksforgeeks.org/functools-module-in-python/)

### 为什么要缓存？

高速缓冲存储器是中央处理器内部的高速存储器，用于加速数据和指令的访问。因此，缓存是一个可以快速访问的地方。结果可以被计算和存储一次，并且从下一次开始，可以在不重新计算的情况下访问结果。因此，在计算量很大的情况下，它很有用。

**@ property 和@cached_property 的区别:**

```py
# Using @property

# A sample class
class Sample():

    def __init__(self):
      self.result = 50

    @property
    # a method to increase the value of
    # result by 50
    def increase(self):
        self.result = self.result + 50
        return self.result

# obj is an instance of the class sample
obj = Sample()
print(obj.increase)
print(obj.increase)
print(obj.increase)
```

**输出**

```py
100
150
200

```

相同的代码，但是现在我们使用@cached_property 代替@property

```py
# Using @cached_property

from functools import cached_property

# A sample class
class Sample():

    def __init__(self):
      self.result = 50

    @cached_property
    # a method to increase the value of
    # result by 50
    def increase(self):
        self.result = self.result + 50
        return self.result

# obj is an instance of the class sample
obj = Sample()
print(obj.increase)
print(obj.increase)
print(obj.increase)
```

**输出**

```py
100
100
100

```

您可以清楚地看到，使用@属性，每次调用 include()方法时都会计算结果的值，这就是它的值增加 50 的原因。但是使用`@cached_property`，结果的值只计算一次，然后存储在缓存中，这样每次调用 include()方法都可以访问，而无需重新计算结果的值，这就是为什么输出每次显示 100。

**但是如何减少执行时间，让程序更快呢？**
考虑以下例子:

```py
# Without using @cached_property

# A sample class
class Sample():

    def __init__(self, lst):
      self.long_list = lst

    # a method to find the sum of the 
    # given long list of integer values
    def find_sum(self):
        return (sum(self.long_list))

# obj is an instance of the class sample
# the list can be longer, this is just
# an example
obj = Sample([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
print(obj.find_sum())
print(obj.find_sum())
print(obj.find_sum())
```

**输出**

```py
55
55
55

```

在这里，假设如果我们传递一个很长的值列表，那么每次调用`find_sum()`方法时都会计算给定列表的总和，从而耗费大量的执行时间，我们的程序最终会变得很慢。我们想要的是，因为列表在创建实例后不会改变，所以如果列表的总和只计算一次，而不是每次当我们调用方法并希望访问总和时计算，那就好了。这可以通过使用@cached_property 来实现

**示例:**

```py
# With using @cached_property

from functools import cached_property

# A sample class
class Sample():
    def __init__(self, lst):
      self.long_list = lst

    # a method to find the sum of the
    # given long list of integer values
    @cached_property
    def find_sum(self):
        return (sum(self.long_list))

# obj is an instance of the class sample
obj = Sample([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
print(obj.find_sum)
print(obj.find_sum)
print(obj.find_sum)
```

**输出**

```py
55
55
55

```

虽然输出是相同的，但它大大减少了执行时间。在创建实例时传递的列表总和只计算一次，并存储在缓存中，此后，每次调用 find_sum()方法时，它都使用相同的、已经计算过的总和值，从而避免了对总和进行昂贵的重新计算。因此，它减少了执行时间，使我们的程序更快。