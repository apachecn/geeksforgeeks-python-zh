# 在 Python 中迭代一个集合

> 原文:[https://www.geeksforgeeks.org/iterate-over-a-set-in-python/](https://www.geeksforgeeks.org/iterate-over-a-set-in-python/)

在 Python 中， [**Set**](https://www.geeksforgeeks.org/python-sets/) 是一个无序的数据类型集合，它是可迭代的、可变的并且没有重复的元素。
有许多方法可以用来迭代一个集合。与其他方法相比，这些方法中的一些提供了更快的执行时间。其中一些方法包括，使用 for/while 循环进行迭代、理解、迭代器及其变体。让我们看看 Python 中迭代集合的所有不同方法。
**每种方法的分析:**
为了解释每种方法/技术的工作原理，每组(随机生成的组)的时间已经被计算了 5 次，以获得每种技术迭代给定组所需时间的粗略估计。random.seed(21)已被添加到每个脚本中，以关注每次执行程序时生成的随机数。使用常量种子有助于我们确定哪种技术最适合给定的随机生成的集合。
**方法#1:** 使用简单 for 循环迭代一个集合。

## 蟒蛇 3

```py
# Creating a set using string
test_set = set("geEks")

# Iterating using for loop
for val in test_set:
    print(val)
```

**输出:**

```py
k
s
e
g
E
```

**分析:**

## 蟒蛇 3

```py
# importing libraries
from timeit import default_timer as timer
import itertools
import random

# Function under evaluation
def test_func(test_set):

    for val in test_set:
        _ = val

# Driver function
if __name__ == '__main__':

    random.seed(21)

    for _ in range(5):
        test_set = set()

        # generating a set of random numbers
        for el in range(int(1e6)):
            el = random.random()
            test_set.add(el)

        start = timer()
        test_func(test_set)
        end = timer()

        print(str(end - start))
```

**输出:**

```py
0.06303901899809716
0.06756918999963091
0.06692574200133095
0.067220498000097
0.06748137499744189
```

**方法#2:** 使用枚举 for 循环迭代一个集合。

## 蟒蛇 3

```py
# Creating a set using string
test_set = set("geEks")

# Iterating using enumerated for loop
for id,val in enumerate(test_set):
    print(id, val)
```

**输出:**

```py
0 E
1 e
2 k
3 g
4 s
```

**分析:**

## 蟒蛇 3

```py
# importing libraries
from timeit import default_timer as timer
import itertools
import random

# Function under evaluation
def test_func(test_set):

    for id, val in enumerate(test_set):
        _ = val

# Driver function
if __name__ == '__main__':

    random.seed(21)
    for _ in range(5):
        test_set = set()

        # generating a set of random numbers
        for el in range(int(1e6)):
            el = random.random()
            test_set.add(el)

        start = timer()
        test_func(test_set)
        end = timer()

        print(str(end - start))
```

**输出** :

```py
0.1306622320007591
0.13657568199778325
0.13797824799985392
0.1386374360008631
0.1424286179972114
```

**方法#3:** 迭代一个集合作为索引列表。

## 蟒蛇 3

```py
# Creating a set using string
test_set = set("geEks")

test_list = list(test_set)

# Iterating over a set as a indexed list
for id in range(len(test_list)):
        print(test_list[id])
```

**输出:**

```py
g
k
E
s
e
```

**分析:**

## 蟒蛇 3

```py
# importing libraries
from timeit import default_timer as timer
import itertools
import random

# Function under evaluation
def test_func(test_set):

    test_list = list(test_set)

    for id in range(len(test_list)):
        _ = test_list[id]

# Driver function
if __name__ == '__main__':

    random.seed(21)
    for _ in range(5):
        test_set = set()

        # generating a set of random numbers
        for el in range(int(1e6)):
            el = random.random()
            test_set.add(el)

        start = timer()
        test_func(test_set)
        end = timer()

        print(str(end - start))
```

**输出** :

```py
0.20036015100049553
0.2557020290005312
0.4601482660000329
0.2161413249996258
0.18769703499856405
```

**方法#4:** 使用理解和列表构造器/初始化器迭代一个集合。

## 蟒蛇 3

```py
# Creating a set using string
test_set = set("geEks")

# Iterating using list-comprehension
com = list(val for val in test_set)
print(*com)
```

**输出:**

```py
k s e g E
```

**分析:**

## 蟒蛇 3

```py
# importing libraries
from timeit import default_timer as timer
import itertools
import random

# Function under evaluation
def test_func(test_set):

    list(val for val in test_set)

# Driver function
if __name__ == '__main__':

    random.seed(21)
    for _ in range(5):
        test_set = set()

        # generating a set of random numbers
        for el in range(int(1e6)):
            el = random.random()
            test_set.add(el)

        start = timer()
        test_func(test_set)
        end = timer()

        print(str(end - start))
```

**输出** :

```py
0.1662169310002355
0.1783527520019561
0.21661155100082397
0.19131610199838178
0.19931397800246486
```

**方法 5:** 使用理解迭代一个集合。

## 蟒蛇 3

```py
# Creating a set using string
test_set = set("geEks")

# Iterating using list-comprehension
com = [print(val) for val in test_set]
```

**输出:**

```py
e
E
g
s
k
```

**分析:**

## 蟒蛇 3

```py
# importing libraries
from timeit import default_timer as timer
import itertools
import random

# Function under evaluation
def test_func(test_set):

    [val for val in test_set]

# Driver function
if __name__ == '__main__':

    random.seed(21)
    for _ in range(5):
        test_set = set()

        # generating a set of random numbers
        for el in range(int(1e6)):
            el = random.random()
            test_set.add(el)

        start = timer()
        test_func(test_set)
        end = timer()

        print(str(end - start))
```

**输出** :

```py
0.11386321299869451
0.111869686999853
0.1092844699996931
0.11223735699968529
0.10928539399901638
```

**方法#6:** 使用地图、λ和列表理解迭代一个集合

## 蟒蛇 3

```py
# importing libraries
from timeit import default_timer as timer
import itertools
import random

# Function under evaluation
def test_func(test_set):

    [map(lambda val: val, test_set)]

# Driver function
if __name__ == '__main__':

    random.seed(21)
    for _ in range(5):
        test_set = set()

        # generating a set of random numbers
        for el in range(int(1e6)):
            el = random.random()
            test_set.add(el)

        start = timer()
        test_func(test_set)
        end = timer()

        print(str(end - start))
```

**输出** :

```py
1.0756000847322866e-05
1.310199877480045e-05
1.269100175704807e-05
1.1588999768719077e-05
1.2522999895736575e-05
```

**方法#7:** 使用迭代器对集合进行迭代。

## 蟒蛇 3

```py
# importing libraries
from timeit import default_timer as timer
import itertools
import random

# Function under evaluation
def test_func(test_set):

    for val in iter(test_set):
        _ = val

# Driver function
if __name__ == '__main__':

    random.seed(21)
    for _ in range(5):
        test_set = set()

        # generating a set of random numbers
        for el in range(int(1e6)):
            el = random.random()
            test_set.add(el)

        start = timer()
        test_func(test_set)
        end = timer()

        print(str(end - start))
```

**输出** :

```py
0.0676155920009478
0.07111633900058223
0.06994135700006154
0.0732101009998587
0.08668379899972933
```

**方法#8:** 使用迭代器和 while 循环对集合进行迭代。

## 蟒蛇 3

```py
# Creating a set using string
test_set = set("geEks")

iter_gen = iter(test_set)

while True:
    try:
        # get the next item
        print(next(iter_gen))

        ''' do something with element '''

    except StopIteration:
        # if StopIteration is raised,
        # break from loop
        break
```

**输出:**

```py
E
s
e
k
g
```

**分析:**

## 蟒蛇 3

```py
# importing libraries
from timeit import default_timer as timer
import itertools
import random

# Function under evaluation
def test_func(test_set):

    iter_gen = iter(test_set)
    while True:
        try:
            # get the next item
            next(iter_gen)
            # do something with element
        except StopIteration:
            # if StopIteration is raised, break from loop
            break

# Driver function
if __name__ == '__main__':

    random.seed(21)
    for _ in range(5):
        test_set = set()

        # generating a set of random numbers
        for el in range(int(1e6)):
            el = random.random()
            test_set.add(el)

        start = timer()
        test_func(test_set)
        end = timer()

        print(str(end - start))
```

**输出:**

```py
0.2136418699992646
0.1952157889973023
0.4234208280031453
0.255840524998348
0.24712910099697183
```

**结论:**
在所有的循环技术中，简单 for 循环迭代和循环遍历迭代器的效果最好，而比较所有的技术，使用 map 搭配 lambda over set 或 iterator of set 的效果最好，给出 10 毫秒内一百万次集合迭代的性能。非常值得注意的是，上面的例子每次迭代只访问一次集合组件，而如果我们增加每次迭代访问集合组件的次数，可能会改变每次迭代所花费的时间。
**注:**上述示例输出中提到的值必然会有所不同。时间消耗变化背后的原因是机器对个人系统处理器处理能力的依赖。