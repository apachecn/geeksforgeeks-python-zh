# python 3

中的转发工具

> 原文:[https://www.geeksforgeeks.org/itertools-in-python3/](https://www.geeksforgeeks.org/itertools-in-python3/)

**Itertools** 是 Python 中的一个模块，它用于迭代数据结构，这些数据结构可以使用 for 循环来跨越。这种数据结构也被称为可数据项。这个模块作为一个快速、内存高效的工具，可以单独使用，也可以组合使用，形成迭代器代数。

## 为什么要用？

该模块包含有效利用计算资源的功能。使用这个模块也有助于增强代码的可读性和可维护性。

## 石斑鱼食谱

石斑鱼()函数可以在 itertools 文档的食谱部分找到。这些食谱是一个很好的灵感来源，可以帮助你利用 itertools。
**例**

## 蟒蛇 3

```
# Python code to demonstrate the
# grouper Recipe
import itertools as it

# defining the grouper function
def grouper(inputs, n, fillvalue = None):
    iters = [iter(inputs)] * n
    return it.zip_longest(*iters, fillvalue = fillvalue)

alpha = ['g', 'e', 'e', 'k', 's', 'f', 'o',
         'r', 'g', 'e', 'e', 'k', 's']
print(list(grouper(alpha, 3)))
```

**输出:**

> [('g '，' e '，' e ')，(' k '，' s '，' f ')，(' o '，' r '，' g ')，(' e '，' e '，' k '，(' s '，无，无)]

## 暴力场景

蛮力是一种解决问题的简单方法，它依靠纯粹的计算能力和尝试各种可能性，而不是先进的技术来提高效率。有不同的强力迭代工具功能，例如:

*   组合()

*   组合 _with_replacement()

*   排列()

### 组合()

[itertools.combinations()](https://www.geeksforgeeks.org/python-itertools-combinations-function/) 函数接受两个参数——一个可迭代的输入和一个正整数 n——并对输入中 n 个元素的所有组合的元组产生一个迭代器。
**例**

## 蟒蛇 3

```
# Python code to demonstrate combinations
import itertools as it

print(list(it.combinations([1, 2], 2)))
```

**输出:**

```
[(1, 2)]
```

### 带替换的组合()

[combinations _ with _ replacement()](https://www.geeksforgeeks.org/python-itertools-combinations_with_replacement/)就像 combinations()一样工作，接受一个可迭代的输入和一个正整数 n，并从输入返回 n 元组元素的迭代器。不同的是，combinations_with_replacement()允许元素在其返回的元组中重复。
**例**

## 蟒蛇 3

```
# Python code to demonstrate combinations_with_replacement
import itertools as it

print(list(it.combinations_with_replacement([1, 2], 2)))
```

**输出:**

```
[(1, 1), (1, 2), (2, 2)] 
```

### 排列()

排列是集合中对象的集合或组合，其中所选对象的顺序或排列很重要。[置换()](https://www.geeksforgeeks.org/python-itertools-permutations/)接受单个可迭代元素，并产生其元素的所有可能的置换(重排)。
**例**

## 蟒蛇 3

```
# Python code to demonstrate permutations
import itertools as it

print(list(it.permutations(['g', 'e', 'k'])))
```

**输出:**

> [('g '，' e '，' k ')，(' g '，' k '，' e ')，(' e '，' g '，' k '，(' e '，' k '，' g ')，(' k '，' g '，' e '，' g')]

## 展平列表列表

将列表(2D)转换为列表(1D)称为展平。展平列表会将所有子列表合并成一个统一的列表。
**例**

## 蟒蛇 3

```
# Python code to demonstrate flattening a list of lists
import itertools as it

list_of_lists = [[1, 2], [3, 4]]
chain_object = it.chain.from_iterable(list_of_lists)

# Return chain object with nested lists separated
# Convert to list to flatten
flattened_list = list(chain_object)

print(flattened_list)
```

**输出:**

```
[1, 2, 3, 4] 
```