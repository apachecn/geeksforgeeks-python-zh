# python–etrtools . chain()

> 原文:[https://www.geeksforgeeks.org/python-itertools-chain/](https://www.geeksforgeeks.org/python-itertools-chain/)

[itertools](https://www.geeksforgeeks.org/python-itertools/) 是 Python 中的一个模块，它有一组用于处理迭代器的函数。它们使得遍历像列表和字符串这样的数据项变得非常容易。其中一个 itertools 功能是**链()**。
**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## 链()函数

这是一个函数，它接受一系列可迭代函数并返回一个可迭代函数。它将所有可迭代表组合在一起，并产生一个可迭代表作为输出。它的输出不能直接使用，因此不能显式转换为 iterables。该函数属于类别迭代器[终止迭代器](https://www.geeksforgeeks.org/python-itertools/#terminate)。
**语法:**

```py
chain (*iterables)
```

链条的内部工作可以按如下方式实现:

```py
def chain(*iterables):
     for it in iterables:
       for each in it:
           yield each
```

**例 1:** 奇数和偶数在单独的列表中。将它们组合成一个新的单一列表。

## 蟒蛇 3

```py
from itertools import chain

# a list of odd numbers
odd = [1, 3, 5, 7, 9]

# a list of even numbers
even = [2, 4, 6, 8, 10]

# chaining odd and even numbers
numbers = list(chain(odd, even))

print(numbers)
```

**Output:** 

```py
[1, 3, 5, 7, 9, 2, 4, 6, 8, 10]
```

**例 2:** 部分辅音在列表中。元音在列表中给出。将它们组合在一起，并对它们进行排序。

## 蟒蛇 3

```py
from itertools import chain

# some consonants
consonants = ['d', 'f', 'k', 'l', 'n', 'p']

# some vowels
vowels = ['a', 'e', 'i', 'o', 'u']

# resultatnt list
res = list(chain(consonants, vowels))

# sorting the list
res.sort()

print(res)
```

**Output:** 

```py
['a', 'd', 'e', 'f', 'i', 'k', 'l', 'n', 'o', 'p', 'u']
```

**示例 3:** 在下面的示例中，每个字符串都被认为是可迭代的，其中的每个字符都被认为是迭代器中的一个元素。这样，每个角色都屈服了

## 蟒蛇 3

```py
from itertools import chain

res = list(chain('ABC', 'DEF', 'GHI', 'JKL'))

print(res)
```

**Output:** 

```py
['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L']
```

**例 4:**

## 蟒蛇 3

```py
from itertools import chain

st1 = "Geeks"
st2 = "for"
st3 = "Geeks"

res = list(chain(st1, st2, st3))
print("before joining :", res)

ans = ''.join(res)
print("After joining :", ans)
```

**Output:**before joining : [‘G’, ‘e’, ‘e’, ‘k’, ‘s’, ‘f’, ‘o’, ‘r’, ‘G’, ‘e’, ‘e’, ‘k’, ‘s’] After joining : GeeksforGeeks 

**chain.from_iterable()函数**
它类似于 chain，但是可以用来从单个 iterable 中链接项目。下面给出的示例说明了这种差异:
**示例 5:**

## 蟒蛇 3

```py
from itertools import chain

li = ['ABC', 'DEF', 'GHI', 'JKL']

# using chain-single iterable.
res1 = list(chain(li))

res2 = list(chain.from_iterable(li))

print("using chain :", res1, end ="\n\n")

print("using chain.from_iterable :", res2)
```

**Output:**using chain : [‘ABC’, ‘DEF’, ‘GHI’, ‘JKL’]using chain.from_iterable : [‘A’, ‘B’, ‘C’, ‘D’, ‘E’, ‘F’, ‘G’, ‘H’, ‘I’, ‘J’, ‘K’, ‘L’] 

**示例 6:** 现在考虑如下列表:

```py
li=['123', '456', '789']
```

你应该把每一个数字都考虑进去，计算出列表的总和。所以答案应该是:

```py
1+2+3+5+6+7+8+9 = 45
```

这可以使用下面的代码轻松实现:

## 蟒蛇 3

```py
from itertools import chain

li = ['123', '456', '789']

res = list(chain.from_iterable(li))

print("res =", res, end ="\n\n")

new_res = list(map(int, res))

print("new_res =", new_res)

sum_of_li = sum(new_res)

print("\nsum =", sum_of_li)
```

**Output:** 

```py
res = ['1', '2', '3', '4', '5', '6', '7', '8', '9']

new_res = [1, 2, 3, 4, 5, 6, 7, 8, 9]

sum = 45
```

为了简化它，我们结合了这些步骤。下面给出了一种优化方法:

## 蟒蛇 3

```py
from itertools import chain

li = ['123', '456', '789']

res = list(map(int, list(chain.from_iterable(li))))

sum_of_li = sum(res)

print("res =", res, end ="\n\n")
print("sum =", sum_of_li)
```

**Output:** 

```py
res = [1, 2, 3, 4, 5, 6, 7, 8, 9]

sum = 45
```