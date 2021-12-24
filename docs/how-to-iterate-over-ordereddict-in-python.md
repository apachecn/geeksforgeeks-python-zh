# 如何在 Python 中迭代 OrderedDict？

> 原文:[https://www . geeksforgeeks . org/如何在 python 中迭代 ordereddct/](https://www.geeksforgeeks.org/how-to-iterate-over-ordereddict-in-python/)

一个 [OrderedDict](https://www.geeksforgeeks.org/ordereddict-in-python/) 是一个子类，它保留了键插入的顺序。*ordereddct*和 *Dict* 的区别在于，普通的 *Dict* 不记录元素的插入方式，而*ordereddct*记住元素的插入顺序。

**说明:**

> **输入:** original_dict = { 'a':1，' b':2，' c':3，' d':4 }
> 
> **输出:** a 1 b 2 c 3 d 4
> 
> **输入:** original_dict = {'sayantan':9，' sanjoy':7，' suresh':5，' rony':2}
> 
> **产量:**萨彦坦 9 桑乔伊 7 苏雷什 5 朗尼 2

**通过 python 中的 Ordereddict 执行迭代的步骤:**

*   用 python 从*集合*导入*订单*。
*   接受*命令的输入。*
*   以下面给出的两种方法中的任何一种迭代*有序循环*:

**接近#1**

迭代通过*命令并打印该值。*

## 蟒蛇 3

```py
# Python code to implement iteration
# over the ordereddict

# import required modules
from collections import OrderedDict

# create dictionary
od = OrderedDict({'a': 1, 'b': 2, 'c': 3, 'd': 4})

# iterating over the ordereddict
for key, value in od.items():
    print(key, value)
```

**输出:**

```py
a 1
b 2
c 3
d 4
```

上述代码也可以写成–

## 蟒蛇 3

```py
# Python code to implement iteration
# over the ordereddict

# import required modules
from collections import OrderedDict

# create dictionary
od = OrderedDict({'a': 1, 'b': 2, 'c': 3, 'd': 4})

# iterating over the ordereddict
for item in od.items():
    print(*item)
```

**输出:**

```py
a 1
b 2
c 3
d 4
```

**接近#2**

遍历枚举对象并打印值。 [enumerate()](https://www.geeksforgeeks.org/enumerate-in-python/) 方法是一种向可枚举对象添加计数器并以枚举对象的形式返回值的方法。

## 蟒蛇 3

```py
# Python code to implement iteration
# over the ordereddict

# import required modules
from collections import OrderedDict

# create dictionary
od = OrderedDict({'a': 1, 'b': 2, 'c': 3, 'd': 4})

# iterating through the enumerate objects
for i, (key, value) in enumerate(od.items()):
    print(key, value)
```

**输出:**

```py
a 1
b 2
c 3
d 4
```